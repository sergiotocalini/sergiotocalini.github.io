---
title: "Centralized Logging"
layout: post
date: 2018-06-22 22:00
image: "/assets/img/projects.webp"
headerImage: true
projects: true
hidden: true
description: "This is a project under development."
category: project
author: sergiotocalini
externalLink: false
tag:
- monitoring
- security
- devops
- devsecops
- logs
---
# Table of Contents
1. [Introduction](#introduction)
2. [Minimum Requirements](#minimum-requirements)
3. [Deployment](#deployment)
4. [Monitoring](#monitoring)
5. [Conclusion](#conclusion)
6. [References](#references)

{:.center}
[![Centralized Logging][diagram]][diagram]
---

# Introduction

{:.justified}
The purpose of this project is to centralize logs from all the servers,
applications and devices that we have on our infrastructure. We will give
minimum requirements recommendation and how you should deploy, monitor and
visualise the logs. For this particular case we will use <b>ELK</b>
(Elasticsearch, Logstash & Kibana) and <b>Rsyslog</b> resources.


# Minimum Requirements

| Service       | Nodes | vCPU | Memory | Disk   |
| :-----------: | :---: | :--: | :----: | :----: |
| Elasticsearch | 3     | 1    | 4 GB   | 50 GB  |
| Logstash      | 1     | 1    | 2 GB   | 50 GB  |
| :-----------: | :---: | :--: | :----: | :----: |
| Total         | 4     | 4    | 14 GB  | 200 GB |

# Deployment

There are many ways to deploy this solution on your environment, but we will
show you the two most common ones.

## Manual

The manual process is simple, we should checkout the plugin that we are trying
to use and execute the deployment script. Let's take the [mysbix] plugin as an
example:

``` bash
~# git clone https://github.com/sergiotocalini/mysbix.git
~# sudo ./mysbix/deploy_zabbix.sh -u "monitor" -p "changeme" -o "localhost"
~# sudo systemctl restart zabbix-agent
```

*__Note__: please take this as an example and also check the dependencies that the
plugin may have.*

## Automated

One way to automated this process is using ansible. I've created some modules to
speed up this process and be able to scalate to multiple servers and services.
Basically we need to set a variable on the servers to specify which applications
have them running on them so then ansible can be able to deploy the right plugin
and the right service on them. Please follow these step to have a [MySQL][mysbix]
database running and fully monitored by zabbix as well as custom script for [Linux][custix].

``` bash
~# git clone https://github.com/sergiotocalini/ansible-playbooks
~# 
```

*__Note__: please note that this is an example and the ansible-playbooks can be
extended in different ways. To have more information please visit the project on
[github][ansible-playbooks].*

# Monitoring


# Conclusion
This project can covered many other services.

# References
* [AWS Solution: Centralized Logging][link01]
* [Digital Ocean: How to centralize logs with Rsyslog, Logstash and Elasticsearch on Ubuntu 14.04][link02]

---
[diagram]: //www.lucidchart.com/publicSegments/view/b45fc179-ca8e-4bb4-995f-24920303fbc1/image.png
[ansible-playbooks]: https://github.com/sergiotocalini/ansible-playbooks
[link01]: //www.digitalocean.com/community/tutorials/how-to-centralize-logs-with-rsyslog-logstash-and-elasticsearch-on-ubuntu-14-04
[link02]: //aws.amazon.com/solutions/implementations/centralized-logging/
