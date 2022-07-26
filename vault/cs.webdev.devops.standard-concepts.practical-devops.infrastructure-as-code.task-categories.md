---
id: nvnzjvsgnhutferjelamh7y
title: Task Categories
desc: ''
updated: 1655650727983
created: 1655650236861
---

1. Infrastructure provisioning
    - The very first step.
    - Spinning up fresh new servers.
    - Doing the network configuration on them.
    - Creating load balancers.
    - Configuring the rest on an infrastructure level.
2. Configuring the already provisioned infrastructure
    - This step takes care to prepare your infrastructure/server with all the necessary application and tools to deploy your application.
    - Also, it helps in managing those dependencies.
3. Deploying the application

With the advent of [[cs.webdev.devops.tools.docker]], the steps 2 and 3 kind of merged as with Docker containers, you package your application and all it's dependencies into an image. So you have all the needed configuration in the image itself.
Therefore, in step 1, i.e. during provisioning, if you install Docker Runtime in all the servers, the further steps gets easier to take care as now you just need to run those containers in the server.

There are two distinctions in the tasks:
![Distinction of phases](/assets/images/2022-06-19-20-28-36.png)
