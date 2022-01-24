---
title: "Managed Lifecycle"
categories:
  - Blog
tags:
  - kubernetes
---

Containerized applications managed by cloud-native platforms have no control over their lifecycle, and to be good cloud-native citizens, they have to listen to the events emitted by the managing platform and adapt their lifecycles accordingly. 

<h2>Problem</h2>

In addition to monitoring the state of a container, the platform sometimes may issue commands and expect the application to react on these. Driven by policies and external factors, a cloud-native platform may decide to start or stop the applications it is managing at any moment. It is up to the containerized application to determine which events are important to react to and how to react. But in effect, this is an API that the platform is using to communicate and send commands to the application.

<h2>Solution</h2>

Real-world applications require more fine-grained interac tions and lifecycle management capabilities. Some applications need help to warm up,
and some applications need a gentle and clean shutdown procedure. For this and other use cases, some events are emitted by the platform that the container can listen to and react to if desired. This events and hooks are all applied at an individual container level.

<h3>SIGTERM Signal</h3>

Whenever Kubernetes decides to shut down a container, whether that is because the Pod it belongs to is shutting down or simply a failed liveness probe causes the container to be restarted, the container receives a SIGTERM signal.

SIGTERM is a gentle poke for the container to shut down cleanly before Kubernetes sends a more abrupt SIGKILL signal. Once a SIGTERM signal has been received, the application should shut down as quickly as possible.

For some applications, this might be a quick termination, and some other applications may have to complete their in-flight requests, release open connections, and clean up temp files, which can take a slightly longer time.

<h3>SIGKILL Signal</h3>

If a container process has not shut down after a SIGTERM signal, it is shut down forcefully by the following SIGKILL signal. Kubernetes does not send the SIGKILL signal immediately but waits for a grace period of 30 seconds by default after it has issued a SIGTERM signal.

This grace period can be defined per Pod. The aim here should be to design and implement containerized applications to be ephemeral with quick startup and shutdown processes.

<h3>Poststart Hook</h3>

Using only process signals for managing lifecycles is somewhat limited. That is why there are additional lifecycle hooks such as postStart and preStop provided by Kubernetes.

The postStart command is executed after a container is created, asynchronously with the primary container’s process. Even if many of the application initialization and warm-up logic can be implemented as part of the container startup steps, post Start still covers some use cases.

The postStart action is a blocking call, and the container status remains Waiting until the postStart handler completes, which in turn keeps the Pod status in the Pending state. 

A use of postStart is to prevent a container from starting when the Pod does not fulfill certain preconditions. For example, when the postStart hook indicates an error by returning a nonzero exit code, the main container process gets killed by Kubernetes.

Since the hook is running in parallel with the container process, it is possible that the hook may be executed before the container has started.

<h3>Prestop Hook</h3>

The preStop hook is a blocking call sent to a container before it is terminated. It has the same semantics as the SIGTERM signal and should be used to initiate a graceful shutdown of the container when reacting to SIGTERM is not possible. The preStop action must complete before the call to delete the container is sent to the container runtime, which triggers the SIGTERM notification.

Even though preStop is blocking, holding on it or returning a nonsuccessful result does not prevent the container from being deleted and the process killed. preStop is only a convenient alternative to a SIGTERM signal for graceful application shutdown and nothing more. 