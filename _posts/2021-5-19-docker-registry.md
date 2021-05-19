---
title: "Docker Registry"
categories:
  - Blog
tags:
  - Docker
---

An image registry is a centralized place where you can upload your images and can also download images created by others. Docker Hub is the default public registry for Docker. Another very popular image registry is Quay by Red Hat. 

You can share any number of public images on Docker Hub for free. People around the world will be able to download them and use them freely. 

Apart from Docker Hub or Quay, you can also create your own image registry for hosting private images. There is also a local registry that runs within your computer that caches images pulled from remote registries.

<h2>Why Use Registries</h2>

You should use the Registry if you want to:
<ul>
<li>tightly control where your images are being stored</li>
<li>fully own your images distribution pipeline</li>
<li>integrate image storage and distribution tightly into your in-house development workflow</li>
</ul>

<h2>Usage</h2>

To pull an image from an on-premises registry, you could run a command similar to:

> docker pull my-registry:9000/foo/bar:2.1

where you pull the version of foo/bar image with tag 2.1 from our on-premise registry located at my-registry domain, port 9000 .

If you used DockerHub instead, and 2.1 was also the latest version, you could run this command to pull the same image locally:

> docker pull foo/bar

<h2>Common Operations Using DockerHub</h2>
<ul>
<li>Login to DockerHub: Running docker login will ask for your DockerHub ID and password.</li>
<li>Searching for an image in a public repository: Use the docker search command with a search term to find all images in public (including official) repositories that match that term.</li>
<li>Pulling an existing image: Use docker pull and specify the image name. By default, the latest version is retrieved, but this behavior can be overridden by specifying a different image tag/version. For example, to pull the (older) version 14.04 of the Ubuntu image:
<br/>
> docker pull ubuntu:14.04
</li>
<li>Pushing a local image: You can push an image by running the docker push command. For example, to push the (latest) local version of my-image to my registry:
<br/>
> docker push my-username/my-image
</li>
</ul>

<h2>Private Registries</h2>

Use cases for running a private registry on-premise (internal to the organization) include:
<ul>
<li>Distributing images inside an isolated network (not sending images over the Internet)</li>
<li>Creating faster CI/CD pipelines (pulling and pushing images from internal network), including faster deployments to on-premise environments</li>
<li>Deploying a new image over a large cluster of machines</li>
<li>Tightly controlling where images are being stored</li>
</ul>

Running a private registry system, especially when delivery to production depends on it, requires operational skills such as ensuring availability, logging and log processing, monitoring, and security. Strong understanding of http and overall network communications is also important.