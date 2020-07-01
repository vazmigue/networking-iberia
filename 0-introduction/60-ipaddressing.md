# IP Addressing

Carving up and assigning private IP address space (RFC 1918 addresses) is a big subject and can be daunting if you have a large enterprise, especially considering large business events with network impact, such as company mergers. Even when you have a centralized IP address management system (IPAM), you will find undocumented address space being used and sometimes finding usable ip space is difficult. However, as network professionals, we want to find large non-fragmented spaces so we can create a well-summarized network. Don't laugh: we got into this because we like challenges, right?
<p>
In our case we found that the 10.0.0.0/11 ip space was available. As a result, we are going to carve up /13's for our Production and Non-Production and we will grab a /16's for our Shared Service and a /16 for our simulated Datacenter.
If you're just getting into CIDR notation, you may wonder, "uhm, what does that mean?" Here's another way of looking at it:

1. **Non-Production CIDR: 10.16.0.0/13** (10.16.0.0 to 10.23.255.255). For this lab, we will fragment 10.16.0.0/13 into smaller Non-Production VPCs: 10.16.0.0/16 and 10.17.0.0/16. The remaining ip space is left untouched for future growth.
2. **Production CIDR: 10.8.0.0/13** (10.8.0.0 to 10.15.255.255). For this lab, we will only use 10.8.0.0/16 for the Production VPC. The remaining ip space is also left untouched.
3. **Shared Services CIDR: 10.0.0.0/16** (10.0.0.0 to 10.0.255.255).


We will also carve out a /16 CIDR for our Datacenter VPC Addressing:

4. **Datacenter VPC CIDR: 10.4.0.0/16** (10.4.0.0 to 10.4.255.255). which will be our Datacenter VPC.

![Speficy Details Screenshot](../images/hybrid-subnets-diagram.png)


