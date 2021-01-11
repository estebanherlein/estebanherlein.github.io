---
title: "Producer-consumer problem"
categories:
  - Blog
tags:
  - software design patterns
  - bug hunting
  - behavioral patterns
---

The producer-consumer problem is a classic example of a multiprocess synchronization problem. The program describes two processes, producer and consumer, both share a finite size buffer. 

The producer's task is to generate a product, store it, and start over; while the consumer (simultaneously) takes products one by one. The problem is that the producer does not add more products than the buffer capacity and that the consumer does not try to take a product if the buffer is empty.

The idea for the solution is the following, both processes (producer and consumer) run simultaneously and “wake up” or “sleep” according to the state of the buffer. 

Specifically, the producer adds products while there is space left and as soon as the buffer is full, he goes to "sleep". When the consumer takes a product, he notifies the producer that he can start working again. Otherwise, if the buffer is emptied, the consumer goes to sleep and the moment the producer adds a product creates a signal to wake him up. A solution can be found using interprocess communication mechanisms, generally semaphores are used. 


<b>An inadequate implementation of the problem can end in a deadlock, where both processes are waiting to be awakened.</b>

This problem can be generalized for multiple consumers and producers.

<h2>Solution using semaphores</h2>

Using semaphores solves the problem of missed calls.
In the solution shown below, two semaphores fillCount and emptyCount are used. The first is the number of objects that exist in the buffer while emptyCount is the number of available spaces where objects can be inserted. fillCount is incremented and emptyCount is decremented when an object is inserted into the buffer. 

If the producer tries to decrement emptyCount when its value is zero, the producer is put to sleep. The next time an object is consumed, the producer wakes up. The consumer works analogously.

<pre>
<code>
semaphore fillCount = 0; // items produced
semaphore emptyCount = BUFFER_SIZE; // remaining space

procedure producer() {
    while (true) {
        item = produceItem();
        down(emptyCount);
            putItemIntoBuffer(item);
        up(fillCount);
    }
}

procedure consumer() {
    while (true) {
        down(fillCount);
            item = removeItemFromBuffer();
        up(emptyCount);
        consumeItem(item);
    }
}
</code>
</pre>

The above solution works perfectly when there is only one producer and one consumer. 

When multiple consumers or producers share the same memory space to store the buffer, the previous solution can lead to results where two or more processes read or write the same region at the same time. 

To understand how this can be possible imagine how the putItemIntoBuffer () function can be implemented. It could contain two actions, one searches for a possible space and the other writes to it. 

If the function can be executed concurrently by multiple producers then the following scenario is possible:

<ol>
<li>Two producers decrement emptyCount</li>
<li>A producer determines the next space where to insert the object.</li>
<li>The second producer determines the next space to insert the object and it turns out to be the same as the first producer.</li>
<li>They both try to write at the same time.</li>
</ol>

To overcome this problem we need to make sure that only one producer is executing the putItemIntoBuffer () method at a time. In other words we need somehow to have a critical section with exclusion. The solution for multiple producers and consumers is shown below.
<pre>
<code>
semaphore mutex = 1;
semaphore fillCount = 0;
semaphore emptyCount = BUFFER_SIZE;

procedure producer() {
    while (true) {
        item = produceItem();
        down(emptyCount);
            down(mutex);
                putItemIntoBuffer(item);
            up(mutex);
        up(fillCount);
    }
}

procedure consumer() {
    while (true) {
        down(fillCount);
            down(mutex);
                item = removeItemFromBuffer();
            up(mutex);
        up(emptyCount);
        consumeItem(item);
    }
}
</code>
</pre>


<h2>Solution using monitors</h2>

The following pseudo-code shows a solution to the problem using monitors. 

Since mutual exclusion is implicit in the monitors, no extra effort is necessary to protect the critical region.

In other words, this variant works with any number of producers and consumers without further modification. The fact that the use of monitors makes the appearance of conflicts much less likely than when using semaphores is relevant.

<pre>
<code>
monitor ProducerConsumer {
    int itemCount
    condition full;
    condition empty;

    procedure add(item) {
        while (itemCount == BUFFER_SIZE) {
            wait(full);
        }

        putItemIntoBuffer(item);
        itemCount = itemCount + 1;

        if (itemCount == 1) {
            notify(empty);
        }
    }
    procedure remove() {
        while (itemCount == 0) {
            wait(empty);
        }

        item = removeItemFromBuffer();
        itemCount = itemCount - 1;

        if (itemCount == BUFFER_SIZE - 1) {
            notify(full);
        }

        return item;
    }
}

procedure producer() {
    while (true) {
        item = produceItem()
        ProducerConsumer.add(item)
    }
}

procedure consumer() {
    while (true) {
        item = ProducerConsumer.remove()
        consumeItem(item)
    }
}

</code>
</pre>
Note the use of the while statement when checking whether the buffer is full or empty. 

With multiple consumers there is a race condition when a consumer is notified that an object has been put into the buffer but another consumer who is waiting on the monitor extracts it from the buffer earlier. 

If instead of a while statement an if is used, many objects can be added to a full buffer or removed from an empty buffer.