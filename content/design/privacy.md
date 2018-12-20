---
title: "Privacy"
date: 2018-12-17T23:15:37-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

One of the challenges for public blockchain is to protect user's privacy. For peer to peer transactions, the from address, the to address as well as the amount are in clear text. It makes all transactions transparent and may not be suitable for business. For example, you might want to hide your service fee from other customers so that you can have more flexibility during negotiation. 

To do that you can ask the buyer to pay to your home bank with an instruction to redistribute the fund to your address. It is suitable for token transactions as well. For the sender, he only pays one transaction fee and potentially saves transaction fees if he/she can group a list of transactions together.

The instructions are encrypted by the home bank encryption public key so only the home bank can read it. Once the home bank distributes the fund to the target address, a comment will be attached so that the target address knows where the fund comes from. The comment is encrypted by the target address public key so that only the receiver can see the comment in clear text. 

The home bank will aggregate multiple transactions to one receiver together so that nobody can use the amount to match the sender. If there is only one transaction, the home bank will split it into a random number of transactions. The home bank can hold the fund to the end of the day or the end of the month to have more chances to aggregate transactions together. 

