# VPC Layout

We are going to provide three types of VPCs:

1. **Non-production VPCs**: We will create some of these to house our Test and Development resources.
2. **Production VPCs**: This is for our live production systems.
3. **Shared Resources**: For resources and services that should be accessible across all VPCs.

In addition, we need a VPC to represent our on-premise environment, a simulated Datacenter:

4. **Datacenter**: In the real world, this would be our existing Datacenter or co-location facility with all the hardware contained, but we are going to make our own version in the cloud!

![Speficy Details Screenshot](../images/hybrid-vpcs-diagram.png)

There are lots of choices for VPC and cccount crchitectures, but they are mostly out-of-scope for this workshop. If you want to know more about multiple VPC architectures, take a look at what Androski Spicer presented at re:Invent 2018 in his [From One to Many: Evolving VPC Design](https://www.youtube.com/watch?v=9Nikqn_02Oc "youtube video").

