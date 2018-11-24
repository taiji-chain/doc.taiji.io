---
title: "Architecture Overview"
date: 2018-11-06T11:14:26-05:00
description: "Taiji Blockchain Architecture"
categories: []
keywords: [architecture]
menu:
  docs:
    parent: "architecture"
    weight: 1
weight: 1
aliases: []
toc: false
draft: false
reviewed: true
---

Taiji Blockchain is aiming both private on-premise and public cryptocurrency. It has very high throughput, low latency and can be scaled up to 10K subchains. It is based on the append-only distributed log architecture and IPFS to publish the chained blocks. 

The topics here are architectural considerations. In a nutshell, architecture is a type of design where the focus is quality attributes and wide(er) scope whereas design focuses on functional requirements and more localized concerns. There is another [design][] section for detail-oriented decisions.

Here is a list of architecture decisions for the Taiji Blockchain:

* [Scalability][]
* [Microservice][]
* [Distributed App][]
* [Event Sourcing][]
* [Security][]
* [Cloud Friendly][]
* [Plugin][]
* [Transaction][]
* [Service Discovery][]
* [Privacy][]
* [Fail-Fast][]



[design]: /design/
[Scalability]: /architecture/scalability/
[Microservice]: /architecture/microservices/
[Distributed App]: /architecture/distributed-app/
[Event Sourcing]: /architecture/event-sourcing/
[Security]: /architecture/security/
[Cloud Friendly]: /architecture/cloud-friendly/
[Plugin]: /architecture/plugin/
[Transaction]: /architecture/transaction/
[Service Discovery]: /architecture/service-discovery/
[Privacy]: /architecture/privacy/
[Fail-Fast]: /architecture/fail-fast/
