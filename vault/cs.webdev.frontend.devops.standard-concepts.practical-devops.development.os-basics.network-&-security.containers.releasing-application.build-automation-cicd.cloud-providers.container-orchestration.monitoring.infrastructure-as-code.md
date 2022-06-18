---
id: 6sjvx596c8b9rd0uvld28qt
title: 9. Infrastructure as Code
desc: ''
updated: 1655496972284
created: 1655496506751
---

![Setting up multiple environments](/assets/images/2022-06-18-01-41-30.png)

Now that we have multiple docker containers running in the production servers, we might need to have separate environments for development and testing with an exact replica of the production environment.

Manually creating those environments is very time consuming and error prone. Hence we need to automate this process by using infrastructure as code tools.

![Infrastructure as code tools](/assets/images/2022-06-18-01-41-59.png)

For that we need two kinds of tools:

1. Infrastructure provisioning e.g. Terraform
2. Configuration management e.g. Ansible, Chef, Puppet etc.

Using these tools will lead the process to be more efficient, less error prone, transparent and easy to replicate and recover.
