---
title: "Event Sourcing"
date: 2018-11-14T06:48:22-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

All distributed applications on the blockchain are based on Event Sourcing and CQRS. If there is no toAddress and value in the ledger, then we are treating the data field in the ledge entry as an event. All events are signed by its owner with an owner address associated. Once an event is on the blockchain, one or more subscribers will provide handlers to process the event and update the state/aggregate related to the event. If a user posts an event nobody subscribes, it is ignored. 

