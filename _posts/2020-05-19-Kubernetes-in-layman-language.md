---
layout: post
title: Kubernetes in layman language!
date: 2020-05-19 10:46
summary: A simple intro to Kubernetes.
category: beginner
---

![](https://upload.wikimedia.org/wikipedia/commons/thumb/3/39/Kubernetes_logo_without_workmark.svg/220px-Kubernetes_logo_without_workmark.svg.png)

Prerequisites: containers

What do I mean by "layman"?

Layman - a person without professional or specialized knowledge in a particular subject.

That's what I was when I started with my Kubernetes journey! I knew a little about docker so, Kubernetes was alien to me, except for a fact that it has something to do with containers and was like docker. But when I got to know about it more, I could applaud the mindful engineers who came upon this marvellous structure.

Let's dive into it then!

The important thing to remember is that everything, every entity of Kubernetes is independent of others. It's really difficult to grasp when we try to understand the whole structure.

# "Why?"

![](https://media.giphy.com/media/1M9fmo1WAFVK0/giphy.gif)

Kubernetes is an open-source container-orchestration system, meaning used for managing the containers. While docker does a pretty good job at keeping records of images and containers, it lacks at managing the scheduling, reporting the health of containers, managing multiple containers at the same time, scaling up and down of containers according to use etc.

When we start managing docker containers at the industry level, things can get messy! There can be multiple containers working at a single time, and keeping track of these containers becomes a really hard job. 

Here, Kubernetes comes to our rescue!

# Some Kubernetes terms

![](https://media.giphy.com/media/3ohjV7896cxaEKCxMI/giphy.gif)

There are different parts of Kubernetes:

- node: node is a physical system(can be a virtual machine) available in Kubernetes, having the hardware components(CPU, RAM).
- cluster: a cluster is a group of nodes, connected in the network.
- pod: pod is the simplest unit of the system. It is headless, meaning alone and can't interact with other member pods, and contains one or more containers, and is allocated resources according to requirement.

So, pods are running on nodes and nodes are part of the cluster. Pods can be running on any available node in the cluster, which has enough resources for a pod to work. Kubernetes system is behind a network, so, you can't communicate to any node or pod directly. You have to take your request through Kubernetes API.

Now, let's dive deeper:

- Master Node: the node which accepts a request from Kubernetes API and performs operations over the system.
- Worker Node: the nodes where the main work is done.
- Namespace: a logical boundary for users to keep related jobs together.
- Services: a window into pods, to let different entities peak into the pods and interact with them.
- Deployment: Keep track of pods deployed and redeploy, if any pod stops, to maintain the count.
- Labels: Labels are key-value pairs which are used by users for adding some metadata to any entity.
- Kubectl: the CLI tool to interact with Kubernetes.

# A glance at architecture

While I have tried to explain the Kubernetes architecture above, below image may help to get a better view of things.

![](https://thenewstack.io/wp-content/uploads/2016/11/Chart_02_Kubernetes-Architecture.png)

# Summary

Many things are not covered above, if you want to learn Kubernetes then I would recommend the Kubernetes interactive course. Also, the hands-on activity would help in getting hang of things.

All the Best! I try to look into it.