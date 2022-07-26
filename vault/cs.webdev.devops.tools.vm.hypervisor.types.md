---
id: vf82df3zquzl3uz9gb6jv6x
title: Types of Hypervisors
desc: ''
updated: 1655664880948
created: 1655663725909
---

![Different Types of VM](/assets/images/2022-06-19-21-30-10.png)

1. Type-1: These are called Bare Metal hypervisors as the Hypervisor is directly installed on a Hardware instead of a Host OS. This is mostly done for big servers. So in this case, instead of talking to the Host OS, it will directly talk with the hardware to use it's resources. e.g. Microsoft Hyper-v and vmware ESXi.
2. Type-2: [[cs.webdev.devops.tools.vm.hypervisor.tools.virtualbox]] is a great example of a Type-2 Hypervisor and it's mostly used for personal use. So in here, you'll have a host OS where you'll install a Hypervisor like VirtualBox which will allow you to create multiple guest OS which will borrow the hardware from the Host OS.
