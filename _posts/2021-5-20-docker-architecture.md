---
title: "Docker Architecture"
categories:
  - Blog
tags:
  - Docker
---

The engine consists of three major components:
<ul>
<li><b>Docker Daemon</b>: The daemon (dockerd) is a process that keeps running in the background and waits for commands from the client. The daemon is capable of managing various Docker objects.</li>
<li><b>Docker Client</b>: The client  (docker) is a command-line interface program mostly responsible for transporting commands issued by users.</li>
<li><b>REST API</b>: The REST API acts as a bridge between the daemon and the client. Any command issued using the client passes through the API to finally reach the daemon.</li>
</ul>

Docker uses a client-server architecture. The Docker client talks to the Docker daemon, which does the heavy lifting of building, running, and distributing your Docker containers

You as a user will usually execute commands using the client component. The client then use the REST API to reach out to the long running daemon and get your work done.

<h2>Everything Works Together</h2>

Before I dive into the explanation of what really happens when you run the docker run hello-world command, let me show you a little diagram:

 <img src="https://i.imgur.com/O8eWTlG.png" alt="docker diagram" > 
 
The events that occur when you execute the command are as follows:

<ol>
<li>You execute docker run hello-world command where hello-world is the name of an image.</li>
<li>Docker client reaches out to the daemon, tells it to get the hello-world image and run a container from that.</li>
<li>Docker daemon looks for the image within your local repository and realizes that it's not there, resulting in the Unable to find image 'hello-world:latest' locally that's printed on your terminal.</li>
<li>The daemon then reaches out to the default public registry which is Docker Hub and pulls in the latest copy of the hello-world image, indicated by the latest: Pulling from library/hello-world line in your terminal.</li>
<li>Docker daemon then creates a new container from the freshly pulled image.</li>
<li>Finally Docker daemon runs the container created using the hello-world image outputting the wall of text on your terminal.</li>
</ol>

It's the default behavior of Docker daemon to look for images in the hub that are not present locally. But once an image has been fetched, it'll stay in the local cache.

If there is a newer version of the image available on the public registry, the daemon will fetch the image again. That :latest is a tag. Images usually have meaningful tags to indicate versions or builds. 