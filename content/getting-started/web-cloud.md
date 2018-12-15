---
title: "Web Client Demo"
date: 2018-12-13T18:13:51-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

For most users, the command line based client is very hard to use, so we have developed a web-based client to let users install it on his/her computer and access it from the browser. To make it even easier for users to try it out, we have deployed an instance at https://demo.taiji.io for testnet only. 

For users who are using the demo client, you create the wallet on the cloud and it is protected by your password so nobody can open it unless they know your wallet address and password. This is good enough for testnet but it is not recommended for mainnet. You should have your own client running on your own computer and don't reveal your wallet to anyone even it is encrypted with a password. 

The web-client has the exact functionality of the console client; however, given it provides a GUI interface, it is much easier to use than the command line. 


There are three major functions for the web-client at the moment and more blockchain distributed applications will be added in the future. Also there is a home page that contains some links to get more information about the blockchain, the taiji currency and distributed applications. 


## Wallet

Before doing anything on the Taiji blockchain, you need to have a wallet. Within the wallet, you have a private key and a public key. You sign all your transactions to the blockchain with your private key, and all your transactions will be associated with an address which contains 40 characters and derived from your public key. 

On the demo site, you create a wallet and it is saved on our cloud server. You have a password to protect your wallet so it can only be opened by your password. This is relatively safe for testnet. 

To create a wallet, click the `Create Wallet` menu and fill in the form and click the `Wallet` button. 

You need to use a very strong password so nobody can guess it as your address is public information once you have transactions on the blockchain and your wallet resides on a shared location.  

You also need to select your geolocation from the dropdown so that your address will be generated for one of the [home banks][] available for the testnet. For the testnet, you can choose any location but for the mainnet, you'd better choose your exact location as [interchain transaction][] fee might be higher than the [inner chain transaction][]. 

As we are using one aging server to host the entire cluster, the wallet creation might take up to 3 minutes as it needs to search within a large key space to find one with address started with the home bank or location you selected. Please be patient. 

Once the wallet is created, you will be redirected to another page will all the information about your wallet. Please copy the information or at least your address to somewhere and keep your password as a secret. You will need the address for all the interaction with the blockchain. 


## Taiji Currency

Once you have a wallet and an address, you can start some transactions. The currency section contains all the functionalities related to Taiji currency transactions. 

Before you can do anything, you need to access the [https://faucet.tiaji.io][] to populate up to 1000 taiji currency to your wallet on a daily basis. It is free for the testnet without any conditions and the mainnet will be based on the contribution for the community. For more info on how to use the faucet site, please refer to the [taiji-faucet getting started][].

### Currency Balance

After you populate some taiji coins to your wallet, you can query your balance from demo site. Click the `Currency Balance` menu and copy/paste your address in the text field and click `Balance` button. The next page will show your balance for all currencies you are holding. Currently there is only one currency taiji available. 

### Currency Transaction

You can also check your transactions based on your address and optionally your currency symbol. Click the `Currency Transaction` menu and copy/paste your address and click the `TRANSACTION` button to get all your transactions associated with the address. If there are more currencies holded in your wallet, they will be all shown up ordered by timestamp. To choose only one currency, you can select the Currency dropdown. As there is only one currency taiji on the blockchain now, the result is the same for now.

### Send Currency




## Token



[home banks]: /concept/home-bank/
[interchain transaction]: /concept/inter-tx/
[inner chain transaction]: /concept/inner-tx/
[https://faucet.tiaji.io]: https://faucet.tiaji.io
[taiji-faucet getting started]: /getting-started/taiji-faucet/
