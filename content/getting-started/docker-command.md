---
title: "Docker Command Line"
date: 2018-11-11T10:20:28-05:00
description: ""
categories: []
keywords: []
slug: ""
aliases: []
toc: false
draft: false
---

If you are familiar with Docker and you don't want to install Java 8 on your computer, you can use Docker command line console. 

### Config

Before starting docker command line console, you need to set up a local config directory so that you generated wallet file can be persisted and backed up from your host computer. 

Also, you need to pass the configuration for testnet or mainnet to the docker container as there is no configuration built into the docker image. 

The easiest way is to use the [standalone console][] repository as its config folder is the same as the docker. 

You can either clone or download the https://github.com/taiji-chain/taiji-console. For details, please follow the steps in [standalone console][]


### Run

Once you have the taiji-console project cloned or unzip on your workspace, go to that folder. You can see there is a config subfolder in it. We need to map the config folder to the docker container so the command can get configuration files and write the generated wallet files to it. 

We also need to pass an env=testnet or evn=mainnet to differentiate the network to run the application. 

```
docker run -it -e env=testnet -v $(pwd)/config:/config networknt/taiji-console wallet send
```
For the rest of the steps, please follow [source code command line][].


[standalone console]: /getting-started/standalone/
[source code command line]: /getting-started/source-code/
