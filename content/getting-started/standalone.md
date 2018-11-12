---
title: "Standalone Command Line"
date: 2018-11-11T10:19:47-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

The standalone command line is very similar to the [source code command line][]. You still need to have Java 8 installed, but you don't need to build from the source code anymore. 

To download it, go to https://github.com/taiji-chain/taiji-console repository. You can clone the entire project into your working directory or you can simple download a zip file if you don't have git installed. Click the green button `Clone or download` and a popup window will be diplayed. 


### Clone

If you want to clone the repo, select `Use HTTPS` and copy the url from the text field and go to the terminal. In your working directory, type the following command. 


```
git clone https://github.com/taiji-chain/taiji-console.git
```

go to the taiji-console folder and create a wallet 

```
./testnet.sh wallet create
```

or send fund to another address

```
./testnet.sh wallet send
```

All other commands are the same, please refer to [source code command line][].

### Download

If you don't have git installed, you can download the zip file. Click the `Download ZIP` link on the same popup window and a zip file will be downloaded to your local. 

Unizp the zip file and you should have a directory called taiji-console-master. Go to that directory and you can run the command line just like you have cloned the repo. 

[source code command line]: /getting-started/source-code/
