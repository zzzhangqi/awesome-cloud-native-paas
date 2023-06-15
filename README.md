
# Awesome Cloud Native Platform

<img align="right" src="img/logo.svg" width="15%"/>

[![Awesome](img/awesome.svg)](https://github.com/sindresorhus/awesome)
[![](img/english.svg)](README.md)
![](https://img.shields.io/github/license/inative-io/awesome-cloud-native)

这是一个关于云原生平台的 Awesome 列表。

不仅仅只是 Awesome 列表，更像是一个云原生平台选型列表，根据我们的需求选择适合我们的云原生平台。

<br/>

## 目录

## PaaS 平台列表

当前列表只展示 100% 开源的、一直有更新、迭代的 PaaS 平台。如有遗漏欢迎提交 [PR](https://github.com/inative-io/awesome-cloud-native-platform/pulls) 补充。

> 只提供免费版的、源码不开源的、长时间不更新迭代的，均不展示。

* [Rancher](https://github.com/rancher/rancher)
* [KubeSphere](https://github.com/kubesphere/kubesphere)
* [Rainbond](https://github.com/goodrain/rainbond)
* [KubeVela](https://github.com/kubevela/kubevela)
* [Portainer](https://github.com/portainer/portainer)

## 产品定位

|            | Slogan                                 | 抽象                                      | 定位                                                      |
| ---------- | -------------------------------------- | ----------------------------------------- | --------------------------------------------------------- |
| Rancher    | Kubernetes 管理平台                    | 容器与 K8s 概念                           | 面向熟悉 K8s 的运维和开发                                 |
| KubeSphere | 面向云原生应用的容器混合云平台         | 容器和 K8s 概念和抽象为主，应用级抽象为辅 | 面向熟悉 K8s 相关技术的运维和开发                         |
| Rainbond   | 不用懂 Kubernetes 的云原生应用管理平台 | 应用级抽象                                | 面向所有运维和开发，平台管理需要懂K8s，使用者不需要懂 k8s |
| KubeVela   | 现代化的软件交付平台                   | 应用级抽象                                | 面向熟悉 K8s 和 OAM 相关技术的运维和开发                  |
| Portainer  | 容器、Kubernetes 管理平台              | 容器与 K8s 概念                           | 面向熟悉 K8s 的运维和开发                                 |

## 产品简介

列表中的每个 PaaS 平台我都使用过，可以说是在企业内部真正使用过。这里将介绍我对这些 PaaS 平台的理解，如有不正确的欢迎提交 [ISSUE](https://github.com/inative-io/awesome-cloud-native-platform/issues) 和 [PR](https://github.com/inative-io/awesome-cloud-native-platform/pulls) 指正。

### Rancher

Rancher 可以说我是非常熟悉了，从最早我开始学习 Docker，使用 Rancher 1.x -> 到学习 Kubernetes，使用 Rancher 2.x，再到 Rancher 的其他开源产品，比如：[K3s](https://github.com/k3s-io/k3s/)、[RKE](https://github.com/rancher/rke)、[RKE2](https://github.com/rancher/rke2)、[Longhorn](https://github.com/longhorn/longhorn)。

#### Rancher 是什么？

Rancher 是一个 Kubernetes 管理工具，让你能在任何地方和任何提供商上部署和运行集群。

Rancher 可以创建来自 Kubernetes 托管服务提供商的集群，创建节点并安装 Kubernetes，或者导入在任何地方运行的现有 Kubernetes 集群。

#### Rancher 安装

Rancher 安装非常简单，[快速安装](https://ranchermanager.docs.rancher.com/pages-for-subheaders/rancher-on-a-single-node-with-docker)只需要一条命令就可以启动。

```bash
docker run -d --restart=unless-stopped \
  -p 80:80 -p 443:443 \
  --privileged \
  rancher/rancher:latest
```

#### Rancher 功能简述

##### 创建集群

第一个必然是创建集群，也是我用的比较多的，相比 Kubeadm 和其他 Kubernetes 安装工具简单很多。Rancher 创建的私有化 Kubernetes 集群使用是 [RKE](https://github.com/rancher/rke)，RKE 是 Kubernetes 的下游发行版，架构简单，解决了 Kubernetes 安装复杂和高可用复杂的问题。