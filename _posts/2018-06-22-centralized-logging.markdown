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
3. [Monitoring](#monitoring)
4. [Conclusion](#conclusion)
5. [References](#references)

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
