---
title: "Processes, kernel threads, user threads, and fibers"
categories:
  - Blog
tags:
  - Linux
---
In computer science, a thread of execution is the smallest sequence of programmed instructions that can be managed independently by a scheduler, which is typically a part of the operating system.

The implementation of threads and processes differs between operating systems, but in most cases a thread is a component of a process. Multiple threads can exist within one process, executing concurrently and sharing resources such as memory, while different processes do not share these resources. 

In particular, the threads of a process share its executable code and the values of its dynamically allocated variables and non-thread-local global variables at any given time. 

<h2>Processes, kernel threads, user threads, and fibers</h2>

Scheduling can be done at the kernel level or user level, and multitasking can be done preemptively or cooperatively. This yields a variety of related concepts.

<h3>Processes</h3>

At the kernel level, a process contains one or more kernel threads, which share the process's resources, such as memory and file handles – a process is a unit of resources, while a thread is a unit of scheduling and execution. Kernel scheduling is typically uniformly done preemptively or, less commonly, cooperatively. At the user level a process such as a runtime system can itself schedule multiple threads of execution. 

If these do not share data, as in Erlang, they are usually analogously called processes, while if they share data they are usually called (user) threads, particularly if preemptively scheduled. 

Cooperatively scheduled user threads are known as fibers; different processes may schedule user threads differently. User threads may be executed by kernel threads in various ways (one-to-one, many-to-one, many-to-many). The term "light-weight process" variously refers to user threads or to kernel mechanisms for scheduling user threads onto kernel threads.

A process is a "heavyweight" unit of kernel scheduling, as creating, destroying, and switching processes is relatively expensive. 

Processes own resources allocated by the operating system. Resources include memory (for both code and data), file handles, sockets, device handles, windows, and a process control block. 

Processes are isolated by process isolation, and do not share address spaces or file resources except through explicit methods such as inheriting file handles or shared memory segments, or mapping the same file in a shared way – see interprocess communication. 

Creating or destroying a process is relatively expensive, as resources must be acquired or released. Processes are typically preemptively multitasked, and process switching is relatively expensive, beyond basic cost of context switching, due to issues such as cache flushing (in particular, process switching changes virtual memory addressing, causing invalidation and thus flushing of an untagged translation lookaside buffer, notably on x86).

<h3>Kernel threads</h3>

A kernel thread is a "lightweight" unit of kernel scheduling. 

At least one kernel thread exists within each process. If multiple kernel threads exist within a process, then they share the same memory and file resources. Kernel threads are preemptively multitasked if the operating system's process scheduler is preemptive.

Kernel threads do not own resources except for a stack, a copy of the registers including the program counter, and thread-local storage (if any), and are thus relatively cheap to create and destroy. Thread switching is also relatively cheap: it requires a context switch (saving and restoring registers and stack pointer), but does not change virtual memory and is thus cache-friendly (leaving TLB valid).

The kernel can assign one thread to each logical core in a system (because each processor splits itself up into multiple logical cores if it supports multithreading, or only supports one logical core per physical core if it does not), and can swap out threads that get blocked. However, kernel threads take much longer than user threads to be swapped.

<h3> User threads</h3>

Threads are sometimes implemented in userspace libraries, thus called user threads. The kernel is unaware of them, so they are managed and scheduled in userspace. Some implementations base their user threads on top of several kernel threads, to benefit from multi-processor machines (M:N model). User threads as implemented by virtual machines are also called green threads.

As user thread implementations are typically entirely in userspace, context switching between user threads within the same process is extremely efficient because it does not require any interaction with the kernel at all: a context switch can be performed by locally saving the CPU registers used by the currently executing user thread or fiber and then loading the registers required by the user thread or fiber to be executed. Since scheduling occurs in userspace, the scheduling policy can be more easily tailored to the requirements of the program's workload.

However, the use of blocking system calls in user threads (as opposed to kernel threads) can be problematic. If a user thread or a fiber performs a system call that blocks, the other user threads and fibers in the process are unable to run until the system call returns. A typical example of this problem is when performing I/O: most programs are written to perform I/O synchronously. When an I/O operation is initiated, a system call is made, and does not return until the I/O operation has been completed. In the intervening period, the entire process is "blocked" by the kernel and cannot run, which starves other user threads and fibers in the same process from executing.

A common solution to this problem (used, in particular, by many of green threads implementations) is providing an I/O API that implements an interface that blocks the calling thread, rather than the entire process, by using non-blocking I/O internally, and scheduling another user thread or fiber while the I/O operation is in progress. Similar solutions can be provided for other blocking system calls. Alternatively, the program can be written to avoid the use of synchronous I/O or other blocking system calls (in particular, using non-blocking I/O, including lambda continuations and/or async/await primitives).

<h3>Fibers</h3>

Fibers are an even lighter unit of scheduling which are cooperatively scheduled: a running fiber must explicitly "yield" to allow another fiber to run, which makes their implementation much easier than kernel or user threads.

A fiber can be scheduled to run in any thread in the same process. This permits applications to gain performance improvements by managing scheduling themselves, instead of relying on the kernel scheduler (which may not be tuned for the application). 

Parallel programming environments such as OpenMP typically implement their tasks through fibers. Closely related to fibers are coroutines, with the distinction being that coroutines are a language-level construct, while fibers are a system-level construct.

<h2>Threads vs. processes pros and cons</h2>

Threads differ from traditional multitasking operating-system processes in several ways:

<ul>
<li>processes are typically independent, while threads exist as subsets of a process</li>
<li>processes carry considerably more state information than threads, whereas multiple threads within a process share process state as well as memory and other resources</li>
<li>processes have separate address spaces, whereas threads share their address space</li>
<li>processes interact only through system-provided inter-process communication mechanisms</li>
<li>context switching between threads in the same process typically occurs faster than context switching between processes</li>
</ul>


Advantages and disadvantages of threads vs processes include:
<ul>
<li>Lower resource consumption of threads: using threads, an application can operate using fewer resources than it would need when using multiple processes.</li>
<li>Simplified sharing and communication of threads: unlike processes, which require a message passing or shared memory mechanism to perform inter-process communication (IPC), threads can communicate through data, code and files they already share.</li>
<li>Thread crashes a process: due to threads sharing the same address space, an illegal operation performed by a thread can crash the entire process; therefore, one misbehaving thread can disrupt the processing of all the other threads in the application.</li>

</ul>