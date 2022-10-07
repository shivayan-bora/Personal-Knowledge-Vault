---
id: omg5ndn53fpltvdn3lf2mvu
title: Docker
desc: ''
updated: 1665072180197
created: 1665058287378
---
The Docker has three major workflow: Build, Ship, Run.

For that, Three main innovations in Docker:

- **The Docker Image (Build):**

Universal app packaging - cross-os - cross-platform - application language agnostic.

Dockerfile: Recipe or instructions to make a docker image/container image. Docker image is now the OCI Standard image.

![Image Layers](/assets/images/2022-10-06-17-49-53.png)

`docker build` command is used to build a docker image from a dockerfile.

Image can also contain  like OS where we need to run the image, the version of the OS, the version of the application, the version of the language, the version of the runtime, etc.

- **The Docker Registry (Ship):**

It's an image registry like maven and npm. It's a place where you can store and share your docker images.

Each image has a unique ID and a tag. The tag is a human-readable name that points to the image ID. ID is a SHA hash of the image.

`docker push` command is used to push an image to a registry.

`docker pull` command is used to pull an image from a registry.

- **The Docker Container (Run):**

Identical runtime environments.

We can pull an image that we need and run it as a container. A container is a running instance of an image.

![Container](/assets/images/2022-10-06-17-55-59.png)

We can create multiple containers from the same image and if we have a bunch of them running, they all are seggregated from each other. Each container will have it's own IP address, it's own hostname, it's own filesystem, it's own memory, it's own CPU, etc.

Turn a previously non-containerized application, turn it into a docker image, put it in a registry, get it whenever you want to run it and finally create a container out of it.

Docker is a two-part system. There is a client and a server. The client is the Docker binary, that we use to interact with the server i.e. Docker engine. The server is the daemon that runs in the background and it's responsible for building, shipping and running the containers.

![Docker System](/assets/images/2022-10-06-21-26-11.png)

`docker run -d -p 8800:80 httpd`: This command will pull the httpd image from the registry, create a container out of it and run it in the background(`-d`). It will also map the port 80 of the container to the port 8800 of the host (`-p`).
