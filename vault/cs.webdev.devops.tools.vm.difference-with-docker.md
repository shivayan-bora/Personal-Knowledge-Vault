---
id: dzfsvycrf2gokfl5drtnnrh
title: Difference with Docker
desc: ''
updated: 1655667128504
created: 1655665957207
---

## OS Layers

![OS Layers](/assets/images/2022-06-20-00-45-35.png)
Usually we have 2 layers in OS. There's an OS kernel and an applications layer. The OS kernel communicates with the hardware like CPU, RAM, storage etc and the applications run on the OS Kernel Layer and are based on the Kernel.

You might have seen, different OS have different applications that's only compatible with that application which is because they're built for a specific Kernel.

## Docker vs VM

![Docker vs VM](/assets/images/2022-06-20-00-46-30.png)
[[cs.webdev.devops.tools.docker]] virtualizes the Applications layer. So when you download a docker image, it contains the applications layer of the OS and some other necessary applications installed on top of it. It uses the Kernel of the host as it doesn't ship with a kernel of it's own.

The VM on the other hand contains both the OS Kernel and the Applications layer. As it contains the entire OS Kernel, when we boot a VM image, it doesn't use the host kernel at all and boots up it's own.

Because of this, there are a few key differences:

1. Docker images are smaller in size as they implement only a single layer.
2. Docker containers start and run much faster as the VM have to boot the new OS Kernel and then the application layer on top of it.
3. You can run VM of any OS on any other host OS. This is not true for Docker images as they don't implement a kernel layer.

![Docker Toolbox](/assets/images/2022-06-20-00-48-02.png)

Let's say you have a Windows OS Kernel and Application layer and you want to run a Linux based Docker image on that host. The Linux based Docker image might not be compatible with a Windows based Kernel. And this is true for Windows versions below 10 and older Mac versions.

Therefore, it's necessary to check if the host can run Docker natively first i.e. if the Host Kernel is compatible with the Docker images. A workaround for that is installing Docker toolbox which abstracts away the kernel to make it possible for the host to run different docker images.
