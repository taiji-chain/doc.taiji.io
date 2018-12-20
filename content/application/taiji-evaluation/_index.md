---
title: "Taiji Evaluation"
date: 2018-12-17T22:48:03-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

This is a blockchain application that allows the community to evaluate a piece of work or other items to give them a quantified value in cryptocurrencies or tokens. 

One of the use cases for us to use this application to evaluate how many tokens a piece of contribution from a community contributor. Once the evaluation is done, we can pay the contributor to the number of tokens equal to the evaluated result. 

To make sure that people are involved in the process, we are going to reward evaluators who gave the number close to the final result. 

Permission is controlled by the following rules currently. 

* The participant must hold taiji greater than an amount. 
* The participant must hold a special token

### EvaluationCreatedEvent

You can choose if to make the evaluation result public or private. 

### EvaluationReceivedEvent

Everybody who has the permission can submit a value in the currency or token specified by the EvaluationCreatedEvent. The submitted value is encrypted with the public key from the evaluation entity address. So everyone can see others submitted their values but there is no way to find out the exact value before the EvaluationClosedEvent is processed. If the evaluation is not anonymous, then the result can be accessed. 

### EvaluationClosedEvent

This is a system event sent by the scheduler. Once the evaluation is created, an expiration date is specified. On the expiration, this EvaluationClosedEvent will be sent automatically to calculate the final result and distributed the fund to the target address and reward to the closed participants. 

### EvaluationDelayedEvent

The owner who creates the evaluation can query how many people have submitted the values. If he/she feels that it needs more time for other participants, this event can be submitted to change the expiration date to another date further away. 


### EvaluationResult

Query the evaluation result after it is closed. 

### EvaluationTransaction

Query all involved transactions for a particular evaluation entity. 
