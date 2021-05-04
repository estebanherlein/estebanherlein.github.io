---
title: "PSR-14: Event Dispatcher"
categories:
  - Blog
tags:
  - php
---

Event dispatching has been around for a long time, in various forms, in many languages. 

All of these systems are a form of "mediated observer". One piece of code emits a message of some kind (an "Event"), and a mediator passes that message to other, decoupled pieces of code (usually called "Listeners"). Sometimes it's mono-directional, other times those other pieces of code can pass data back to the caller in some fashion. They are all, of course, different and incompatible.

That creates a problem for stand-alone libraries that want to be able to connect to multiple frameworks and applications. Many libraries make themselves extensible by emitting events in some form or another for other code to tie into; however, that mediating layer is essentially proprietary. A library that injects the Symfony EventDispatcher is then coupled to Symfony; using it anywhere else requires installing EventDispatcher and bridging to whatever that framework's event system is. A library that calls Drupal's module_invoke_all() hook system is then coupled to Drupal. And so on.

The goal of PSR-14, then, is to abstract that dependency. It allows libraries to expose themselves to extension via a thin generic layer, which then makes it very simple to drop them into Symfony, Zend Framework, Laravel, TYPO3, eZ Platform, Slim, or any other environment without any extra overhead. As long as that environment has some PSR-14 compatible implementation, it will work.

<h2>Definitions</h2>
<ul>
<li><b>Event</b> - An Event is a message produced by an Emitter. It may be any arbitrary PHP object.</li>
<li><b>Listener</b> - A Listener is any PHP callable that expects to be passed an Event. Zero or more Listeners may be passed the same Event. A Listener MAY enqueue some other asynchronous behavior if it so chooses.</li>
<li><b>Emitter</b> - An Emitter is any arbitrary code that wishes to dispatch an Event. This is also known as the "calling code". It is not represented by any particular data structure but refers to the use case.</li>
<li><b>Dispatcher</b> - A Dispatcher is a service object that is given an Event object by an Emitter. The Dispatcher is responsible for ensuring that the Event is passed to all relevant Listeners, but MUST defer determining the responsible listeners to a Listener Provider.</li>
<li><b>Listener Provider</b> - A Listener Provider is responsible for determining what Listeners are relevant for a given Event, but MUST NOT call the Listeners itself. A Listener Provider may specify zero or more relevant Listeners.</li>
</ul>

<h2>Events</h2>

Events are objects that act as the unit of communication between an Emitter and appropriate Listeners.

Event objects MAY be mutable should the use case call for Listeners providing information back to the Emitter. However, if no such bidirectional communication is needed then it is RECOMMENDED that the Event be defined as immutable; i.e., defined such that it lacks mutator methods.

Implementers MUST assume that the same object will be passed to all Listeners

<h2>Listeners</h2>

A Listener may be any PHP callable. A Listener MUST have one and only one parameter, which is the Event to which it responds. Listeners SHOULD type hint that parameter as specifically as is relevant for their use case; that is, a Listener MAY type hint against an interface to indicate it is compatible with any Event type that implements that interface, or to a specific implementation of that interface.

<h2>Dispatcher</h2>

A Dispatcher is a service object implementing EventDispatcherInterface. It is responsible for retrieving Listeners from a Listener Provider for the Event dispatched, and invoking each Listener with that Event.

A Dispatcher:
<ul>
<li>MUST call Listeners synchronously in the order they are returned from a ListenerProvider.</li>
<li>MUST return the same Event object it was passed after it is done invoking Listeners.</li>
<li>MUST NOT return to the Emitter until all Listeners have executed.</li>
</ul>

<h2>Listener Provider</h2>

A Listener Provider is a service object responsible for determining what Listeners are relevant to and should be called for a given Event. It may determine both what Listeners are relevant and the order in which to return them by whatever means it chooses. That MAY include:
<ul>
<li>Allowing for some form of registration mechanism so that implementers may assign a Listener to an Event in a fixed order.</li>
<li>Deriving a list of applicable Listeners through reflection based on the type and implemented interfaces of the Event.</li>
<li>Generating a compiled list of Listeners ahead of time that may be consulted at runtime.</li>
<li>Implementing some form of access control so that certain Listeners will only be called if the current user has a certain permission.</li>
<li>Extracting some information from an object referenced by the Event, such as an Entity, and calling pre-defined lifecycle methods on that object.</li>
<li>Delegating its responsibility to one or more other Listener Providers using some arbitrary logic.</li>
</ul>
