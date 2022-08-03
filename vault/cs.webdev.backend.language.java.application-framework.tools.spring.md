---
id: fzoyvbxbp4866qbcie1y7rq
title: Spring
desc: ''
updated: 1659252156186
created: 1659162727789
---

A typical application structure looks like this:

![Layers of Application](/assets/images/2022-07-30-17-35-27.png)

**Web Layer**: Takes care of the UI or the [[cs.webdev.frontend]]. If the UI needs some data to show to the user, it calls the Business layer.

**Business Layer**: Place where your business logic lies. If business layer needs some data, it calls some class which is present inside the Data Layer.

**Data Layer**: Talks with the external interfaces as well as the Database.

So, Web Layer --> Dependent on --> Business Layer --> Dependent on --> Data Layer

Spring framework instantiates objects and populates the dependencies. It's us developers who are responsible for telling the framework on what are the objects it needs to manage and what are it's dependencies.
