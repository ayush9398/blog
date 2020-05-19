---
layout: post
title: Kafka  Quickstart with python
date: 2020-05-19 10:46
summary: Kubernetes in layman language!
categories: beginner, docker
---

Prerequisites: containers

What do I mean by layman?

Layman - a person without professional or specialized knowledge in a particular subject.

That what I was when I started with my Kuberntes journey! I knew a little about docker so, Kuberntes was totally alien to me, except of a fact that it has something to do with containers and was like docker. But when I got to know about it more, I could really applaud the mindful engineers who came upon this marvellous structure.

Let's dive into it then!

The important thing to remember is that everything, every entity of Kubernetes is independent of other. It's really difficult to grasp when we try to understand the whole structure.

# The Why?

![](https://media.giphy.com/media/1M9fmo1WAFVK0/giphy.gif)

Kubernetes is an open-source container-orchestration system, meaning used for managing the containers. While docker does pretty good job at keeping records of images and containers, it lacks at managing the scheduling, reporting health of containers, managing multiple containers at the same time, scaling up and down of containers according to use etc.

When we start managing docker containers at industry level, things can get messy! There can be multiple containers working at a single time, and keeping track of these containers becomes really hard job. 

Here, Kubernetes comes to our rescue!

# Some Kubernees terms

![](https://media.giphy.com/media/3ohjV7896cxaEKCxMI/giphy.gif)

There are different parts of Kubernetes:

- node: node is a physical system(can be a vistual machine) available in Kubernetes, having the hardware components(CPU, RAM).
- cluster: cluster is a group of nodes, connected together.
- pod: pod is the simplest unit of the system. It is headless, meaning alone and can't interact with other member pods, and contains one or more containers, and is allocated resources according to requirement.

So, pods are running on nodes and nodes are part of cluster. Pods can be running on any availale node in cluster, which has enough resources for pod to work. Kubernetes system is behind a network, so, you can't directly communicate to any node or pod directly. You have to take your request through kubernetes api.

Now, lets dive deeper:

- Master Node: the node which accepts request from kubernetes api and perform operations over the system.
- Worker Node: the nodes where the main work is done.
- Namespace: a logical boundary for users to keep the related jobs together.
- Services: window into pods, to let different entities peak into the pods and interact with them.
- Deployment: Keep track of pods deployed and redeploy, if any pod stops, to amintain the count.
- Labels: Labels are key-value pairs which are used by users for adding some metadata to any entity.
- Kubectl: the cli tool to interact with kubernetes.

# A glance at architecture

While I have tried to explain the Kubernetes architecture above, below image may help to get a better view of things.

![](http://thenewstack.io/wp-content/uploads/2016/11/Chart_02_Kubernetes-Architecture.png)

# Summary

There are many things that are not covered above, if you want to learn kubernetes then I would recommend the Kubernetes interactive course. Also, more hands-on activity would help in getting hang of things.

All the Best!