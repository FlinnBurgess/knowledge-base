# Overview

Docker is a tool for implementing containers. Containers are a virtualisation method for running multiple apps/services on a single machine.

Containers are a logical progression from traditional virtual machine \(VM\) based virtualisation. Instead of creating a virtual machine for each service and provisioning each with it's own dependencies and operating systems, containers allow us to implement each on a single operating system. Also, while VMs virtualize at a hardware level, containers do it at the operating system level.

One of the main benefits of containers is their ability to isolate dependencies. Let's say we want to deploy one app which relies on a particular version of Python, and another app which relies on a different version of Python. Deploying both on the same machine/VM would be difficult. But with containers, we can specify the resources available to them, so we can easily tailor a container to the technical requirements of the app running on it.

Another benefit is their scalability. To get a new service running we simply deploy a new container on the system, rather than having to fire up a new VM and provision it.

