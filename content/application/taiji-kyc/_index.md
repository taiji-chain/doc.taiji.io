---
title: "KYC - Know Your Client"
date: 2018-12-17T20:42:32-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

For most cryptocurrencies, there is no user identifier but just a unique meaningless address. It is very hard to verify if the address you're trying to send fund to is the right one or not. Once you are doing business online, it might be easier to give your customer an email or id so that they can find you on the blockchain by a search. If you are a business owner, you want your business to be categorized and listed in the marketplace. Also, everybody and every business want to put a description to show people more information about the user or company. 

There are several events that you can send to the blockchain to manipulate your KYC. 

### KycCreatedEvent

The event represents the creation of a new KYC entry on the blockchain. You can choose a unique id so that other users can use it to identify you. You need a valid email address to create a KYC entry, and the kyc-reader application will verify the email. 

As part of the KYC, an encryption public key will be saved there so that other people can use it to encrypt data. 

Other information for the KYC will contain the type of the address. There are two types: personal and business. 

Name, tags, and description are three extra fields that can be updated with KycUpdatedEvent. 
 

### KycUpdatedEvent

Most fields are not updatable in the KYC but there are three fields name, tags and description can be updated with this event. 


### KycVerifiedEvent

Once the KYC is created, the kyc-reader will send an email with a link to verify the email address. Once the user clicks the link, the email will be verified and the verified flag is set to true from the default false value. 

### KycMigratedEvent

Migrate KYC entry from one address to another. 

### KycInfo

This is the query to get the KYC info for a particular address. 

