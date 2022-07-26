---
id: 87el50jec7o4obdyxvmpqf6
title: 5. Build Automation and CI/CD
desc: ''
updated: 1655477513671
created: 1655465861502
---

![Build Automation and CI/CD](/assets/images/2022-06-17-20-06-06.png)

When the application feture gets pushed into the repository, we need to run the tests. Once that's done, we need to build and package the application into an executable that the server can run.

This is where Build tools and Package Manager comes in the picture e.g. for Java Applications we have Maven, Gradle etc. and for JavaScript applications we have [[npm|cs.webdev.frontend.language.js.tools.npm]]

As more and more companies are adopting Docker for containerizing their applications, we need to learn how to create docker images and the next step would be to push this image into an artifact repository e.g. Docker Hub or Nexus.

Of course you wouldn't want this process to be a manual process and because of that we need a build automation tool like GitLab, Github actions and Jenkins (one of the most popular build automation tools).

You would need to connect this pipeline to the [[git|cs.webdev.devops.tools.git]] repository to get the code.

This first part is the continuous integration process which consists of pulling the code changes from git, running tests, performing builds and packaging the app, building an image and pushing it into the repository.

Then this image is deployed on the server which is a part of the continuous deployment process.

![CI/CD Pipeline](/assets/images/2022-06-17-20-21-43.png)
