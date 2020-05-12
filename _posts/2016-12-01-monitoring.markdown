---
title: "Monitoring"
layout: post
date: 2016-12-01 22:00
image: "/assets/img/projects.webp"
headerImage: true
projects: true
hidden: true # don't count this post in blog pagination
description: "This is a project under development."
category: project
author: sergiotocalini
externalLink: false
tag:
- monitoring
- devops
- devsecops
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

# Services

There are many services already covered by this project but it is also possible
to extend the support to more services.

## What services are covered until now?

| #  | Service         | Plugin      | OS Platform    |
| -- | --------------- | :---------: | :------------: |
| 01 | ArangoDB        | [aranix]    | UNIX / Linux   |
| 02 | Bind            | [bindix]    | UNIX / Linux   |
| 03 | Docker          | [zocker]    | UNIX / Linux   |
| 04 | Dovecot         | [doveix]    | UNIX / Linux   |
| 05 | Elasticsearch   | [elasix]    | UNIX / Linux   |
| 06 | GlusterFS       | [glusix]    | UNIX / Linux   |
| 07 | HAProxy         | [habbixy]   | UNIX / Linux   |
| 08 | IPSec           | [zipsec]    | UNIX / Linux   |
| 09 | Java Springboot | [zaring]    | UNIX / Linux   |
| 10 | Jenkins         | [jenkix]    | UNIX / Linux   |
| 11 | KVM             | [virbix]    | UNIX / Linux   |
| 12 | Keepalived      | [keepax]    | UNIX / Linux   |
| 13 | Logstash        | [lostix]    | UNIX / Linux   |
| 14 | MSSQL           | [msqlix]    | Windows        |
| 15 | MySQL           | [mysbix]    | UNIX / Linux   |
| 16 | Nginx           | [znginx]    | UNIX / Linux   |
| 17 | OpenLDAP        | [zaldap]    | UNIX / Linux   |
| 18 | OpenVPN         | [zaovpn]    | UNIX / Linux   |
| 19 | Oracle DB       | [zabora]    | UNIX / Linux   |
| 20 | PostgreSQL      | [zapgix]    | UNIX / Linux   |
| 21 | Python Gunicorn | [gunbix]    | UNIX / Linux   |
| 22 | Redis           | [zedisx]    | UNIX / Linux   |
| 23 | Seafile         | [seabix]    | UNIX / Linux   |
| 24 | Splunk          | [spluix]    | UNIX / Linux   |
| 25 | UNIX / Linux    | [custix]    | UNIX / Linux   |
| 26 | Windows         | [custiw]    | Windows        |

## How can I add more services?

Following these steps you will be able to extend the plugin list.


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

# Conclusion
This project can covered many other services.

---
[ansible-playbooks]: https://github.com/sergiotocalini/ansible-playbooks
[aranix]: https://github.com/sergiotocalini/aranix
[bindix]: https://github.com/sergiotocalini/bindix
[zocker]: https://github.com/sergiotocalini/zocker
[doveix]: https://github.com/sergiotocalini/doveix
[elasix]: https://github.com/sergiotocalini/elasix
[glusix]: https://github.com/sergiotocalini/glusix
[habbixy]: https://github.com/sergiotocalini/habbixy
[zipsec]: https://github.com/sergiotocalini/zipsec
[zaring]: https://github.com/sergiotocalini/zaring
[jenkix]: https://github.com/sergiotocalini/jenkix
[virbix]: https://github.com/sergiotocalini/virbix
[keepax]: https://github.com/sergiotocalini/keepax
[lostix]: https://github.com/sergiotocalini/lostix
[msqlix]: https://github.com/sergiotocalini/msqlix
[mysbix]: https://github.com/sergiotocalini/mysbix
[znginx]: https://github.com/sergiotocalini/znginx
[zaldap]: https://github.com/sergiotocalini/zaldap
[zaovpn]: https://github.com/sergiotocalini/zaovpn
[zabora]: https://github.com/sergiotocalini/zabora
[zapgix]: https://github.com/sergiotocalini/zapgix
[gunbix]: https://github.com/sergiotocalini/gunbix
[zedisx]: https://github.com/sergiotocalini/zedisx
[seabix]: https://github.com/sergiotocalini/seabix
[spluix]: https://github.com/sergiotocalini/spluix
[custix]: https://github.com/sergiotocalini/custix
[custiw]: https://github.com/sergiotocalini/custiw
