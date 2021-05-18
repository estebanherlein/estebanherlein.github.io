---
title: "Docker images"
categories:
  - Blog
tags:
  - Docker
---

Images are multi-layered self-contained files that act as the template for creating containers. They are like a frozen, read-only copy of a container. Images can be exchanged through registries.

In the past, different container engines had different image formats. But later on, the Open Container Initiative (OCI) defined a standard specification for container images which is complied by the major containerization engines out there. This means that an image built with Docker can be used with another runtime like Podman without any additional hassle.

Containers are just images in running state. When you obtain an image from the internet and run a container using that image, you essentially create another temporary writable layer on top of the previous read-only ones.

<b>Images are multi-layered read-only files carrying your application in a desired state inside them.</b>

<h2>Anatomy of a Docker Image</h2>

A Docker image is made up of a collection of files that bundle together all the essentials – such as installations, application code, and dependencies – required to configure a fully operational container environment. 

You can create a Docker image by using one of two methods:
<ul>
<li><b>Interactive</b>: By running a container from an existing Docker image, manually changing that container environment through a series of live steps, and saving the resulting state as a new image.</li>
<li><b>Dockerfile</b>: By constructing a plain-text file, known as a Dockerfile, which provides the specifications for creating a Docker image.</li>
</ul>

Let’s focus on the most important Docker image concepts.

<h3>Container Layer</h3>

Each time Docker launches a container from an image, it adds a thin writable layer, known as the container layer, which stores all changes to the container throughout its runtime. 

As this layer is the only difference between a live operational container and the source Docker image itself, any number of like-for-like containers can potentially share access to the same underlying image while maintaining their own individual state.

<h3>Image Layers</h3>

Each of the files that make up a Docker image is known as a layer. These layers form a series of intermediate images, built one on top of the other in stages, where each layer is dependent on the layer immediately below it. 

The hierarchy of your layers is key to efficient lifecycle management of your Docker images. Thus, you should organize layers that change most often as high up the stack as possible. 

This is because, when you make changes to a layer in your image, Docker not only rebuilds that particular layer, but all layers built from it. Therefore, a change to a layer at the top of a stack involves the least amount of computational work to rebuild the entire image.

<h3>Parent Image</h3>

In most cases, the first layer of a Docker image is known as the parent image. It’s the foundation upon which all other layers are built and provides the basic building blocks for your container environments. You can find a wide variety of ready-made images for use as your parent image on the public container registry Docker Hub. You can also find them on a small number of third-party services, such as the Google Container Registry. Alternatively, you can use one of your own existing images as the basis for creating new ones.

A typical parent image may be a stripped-down Linux distribution or come with a preinstalled service, such as a database management system (DBMS) or a content management system (CMS).

<h3>Base Image</h3>

In simple terms, a base image is an empty first layer, which allows you to build your Docker images from scratch. Base images give you full control over the contents of images, but are generally intended for more advanced Docker users.

<h3>Docker Manifest</h3>

Together with a set of individual layer files, a Docker image also includes an additional file known as a manifest. This is essentially a description of the image in JSON format and comprises information such as image tags, a digital signature, and details on how to configure the container for different types of host platforms.User-added image