---
id: cjsiux2a6kkr9zo4fcpg7oq
title: Why Companies Use Virtualization
desc: ''
updated: 1655665849886
created: 1655665205206
---

1. One of the reasons of using Virtualization with multiple OS on a system, is the efficient usage of hardware resources. We can use all the resources of a performant big server. Users can choose any number of resource combinations like CPU, RAM, storage etc.

2. Abstraction of OS from the hardware: Without virtualization, imagine you have to setup a server. You would install an OS in the hardware and manually install all the applications like PostgreSQL etc. on the machine. This OS is very tightly coupled with the hardware and if for some reason the hardware stops working, it will crash the entire structure and nothing will work. You'll basically need to replace the server and do everything from scratch. This implies there's a single point of failure for the whole architecture.
![Abstraction of OS from the hardware](/assets/images/2022-06-20-00-34-52.png)
In case of virtualization, you'll have a virtual machine image which is a portable file containing the OS and all the necessary dependencies, applications etc. So, you can have backups of your entire OS which are called snapshots. In case the server stops working and corrupts your virtual image, you can take the snapshot and run in on a different server with a [[cs.webdev.frontend.devops.tools.vm.hypervisor]] installed in it.

3. It's easier to secure your application and your work.
4. You can move it around machines(portable), without it being dependent on any physical server.
