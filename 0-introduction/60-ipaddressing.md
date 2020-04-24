# IP Addressing

Carving up and assigning private IP address space (RFC 1918 addresses) is a big subject and can be daunting if you have a large enterprise, especially considering large business events with network impact, such as mergers. Even when you have a centralized IP address management system (IPAM), you will find undocumented address space being used and sometimes finding usable space is difficult. Despite of this, we as network professionals want to find large non-fragmented spaces so we can create a well-summarized network. Don't laugh: we got into this because we like challenges, right?
<p>
In our case we found that the 10.0.0.0/11 space was available (spoiler alert: the previous statement is fictional in every network but this one, yet representative). As a result, we are going to carve up /13's for our Production and Non-Production and we will grab a /16's for our Shared Service and a /16 for our simulated Datacenter.
If you're just getting into CIDR notation, you may wonder, "um, what does that mean?" Here's another way of looking at it:

1. **Non-Production CIDR: 10.16.0.0/13** (10.16.0.0 to 10.23.255.255), which we can carve into eight /16 subnets, one for each of our VPCs.
2. **Production CIDR: 10.8.0.0/13** (10.8.0.0 to 10.15.255.255), which we can also carve into eight /16 subnets.
3. **Shared Services CIDR: 10.0.0.0/16** (10.0.0.0 to 10.0.255.255), which we will use for 1 Datacenter Services VPC.


We will also carve out a /16 CIDR for our Datacenter VPC Addressing:

4. **Datacenter VPC CIDR: 10.4.0.0/16** (10.4.0.0 to 10.4.255.255). which will be our Datacenter VPC.

![Speficy Details Screenshot](../images/hybrid-subnets-diagram.png)


