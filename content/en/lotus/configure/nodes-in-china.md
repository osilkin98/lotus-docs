---
title: "Nodes in China"
description: "This guide provides a few tips for users in China to get around some of the bandwidth issues or slowness they can suffer when building and running Lotus."
lead: "This guide provides a few tips for users in China to get around some of the bandwidth issues or slowness they can suffer when building and running Lotus."
draft: false
menu:
    lotus:
        parent: "lotus-configure"
aliases:
    - /docs/set-up/nodes-in-china/
toc: true
---

## Speed up proof parameter download for first boot

Running Lotus requires the download of chain's _proof parameters_ which are large files which by default are hosted outside of China and very slow to download there. To get around that, users should set the following environment variable when running either of `lotus`, `lotus-miner` and `lotus-worker`:

```shell
export IPFS_GATEWAY=https://proof-parameters.s3.cn-south-1.jdcloud-oss.com/ipfs/
```

## Speed up Go module download during builds

Building Lotus requires downloading a few Go modules. These are usually hosted on Github, which has very low bandwidth from China. To fix this use a local proxy by setting the following variable **before** running Lotus:

```shell
export GOPROXY=https://goproxy.cn
```
