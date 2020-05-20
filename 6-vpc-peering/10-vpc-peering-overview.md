# VPC Peering Overview

A VPC peering is a networking connection between two VPCs that enables you to route traffic between them using private IPv4 addresses or IPv6 addresses. Instances in either VPC can communicate with each other as if they are within the same network. You can create a VPC peering connection between your own VPCs, or with a VPC in another AWS account. The VPCs can be in different regions (also known as an inter-region VPC peering).

**Why would I need to use VPC Peering if I have Transit Gateway?**

While for most use cases customers choose to provide inter-VPC connectivity via Transit Gateway, there might be a few cases in which VPC-peering is more suitable:

1. Customers with just two, three or very few VPCs and no plans to extend those.

1. Multiple applications in a VPC that have no VPN or TGW access to other VPCS.

1. The need for additional bandwidth for high-performance applications. While Transit Gateway provides over 40Gbps per Availability Zone, VPC Peering within the same regions is nearly unlimited, only limited by the individual Instances and services bandwidth limits. *i.e. you could have 100 instances of i3.8xlarge with 10Gbps each talking to 100 instances i3.8xlarge in another VPC. Over VPC peering, they could be running at near line rate to each other. *Note: each TCP flow is limited to 5Gbps, so to achieve >5Gbps you need to have multiple flows between two hosts.**

In this lab, we will peer our **NP1** and **NP2** VPCs and run a quick test between a couple of instances via VPC Peering instead of using the Transit Gateway:
	![VPC peering](../images/peer-np1tonp2diagram.png)