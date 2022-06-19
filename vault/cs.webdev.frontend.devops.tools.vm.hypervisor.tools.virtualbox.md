---
id: ngk5med9lb7wug5wi9ugwhu
title: VirtualBox
desc: ''
updated: 1655664344328
created: 1655664046873
---

VirtualBox takes hardware resources from a Host OS and creates a virtual CPU, virtual RAM, virtual storage etc. for each virtual machine.

A point to remember is that, we can only give resources to the VirtualBox that we actually have in the host OS.

So effectively, we're sharing the hardware resources on one machine to run multiple virtual machines.

These virtual machines are completely isolated and don't see each other. It thinks that it's just running independently inside that host computer.

So, if something breaks inside the VM or someone hacks inside that VM, it doesn't affect the host machine.
