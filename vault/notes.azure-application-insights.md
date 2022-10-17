---
id: 8qq0a593jw6bxn0gwrgix36
title: Azure Application Insights
desc: ''
updated: 1665637334584
created: 1665637334584
---

## What is Azure Application Insights?

It's an everyday tool for developers and DevOps teams to monitor their applications. It provides a way to monitor your application's performance, availability, and usage. It also provides a way to monitor your application's dependencies and external services.

It's a part of a bigger service called Azure Monitor.

## How it works?

![Monitoring overview](/assets/images/2022-10-13-11-00-36.png)

A simple web application might have multiple pages. Those pages will call the backend web service to get the data. This webservice on the other hand will fetch that data from databases, external APIs and internal APIs. To setup monitoring for this kind of architecture might be a little bit tricky.

This is where Azure Application Insights (AI) comes in. You can hook up your frontend with AI which will monitor your user interactions like Google Analytics and some of the requests to the back-end services.

We can also install the AI SDK on our backend web services and the internal APIs to grab the monitoring of those services which can be both azure and non-azure services.

Notice, you can't install it on an external API or SQL if you don't have any control over it but it will still let you track the dependency calls to those services.

Once you get the data in AI, you can do a lot of things with it like create alerts, connect it with PowerBI, Visual Studio, Azure DevOps, etc.

## What does it track?

Key Metrics:

1. Request rates
2. Dependency rates
3. Exceptions logging: It can give you the full trace of the exception as well as the user interaction that caused the exception.
4. Page views
5. Load performance
6. HTTP(s) calls
7. User and session counts
8. Performance counts
9. Host diagnostics
10. Diagnostic trace logs
11. Custom events

![Application Map](/assets/images/2022-10-13-11-23-07.png)

This is a visual diagram of our application and the data based on the logs itself. This visualizes how the application is working solely on the basis of the logs.

![Smart Detection](/assets/images/2022-10-13-11-25-11.png)

This is a view to grab log detection for failures and performance anomalies. So imagine, you close up for the day and your application is running. For all the anomalies and failures, the Smart Detection view will grab logs and show events based on the category and you can even set up alerts and notifications for those events.

![Usage Analytics](/assets/images/2022-10-13-11-29-38.png)

Imitates Google Analytics.

![](/assets/images/2022-10-13-11-29-00.png)
