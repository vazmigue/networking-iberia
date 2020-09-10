# Network Manager Route Analyzer

As our network scales it can be hard to understand all routing paths that our infrastructure components will take. Network Manager route analyzer enables us to quickly understand which paths a connection between two IP's will take.

### Route Analyzer

1. Click on the **Route Analyzer** tab. Under the *Source* *Transit Gateway attachment* select **P1 attach** (our production vpc). For the *Destination* *Transit Gateway attachment* select one of the **VPN** attachements we created.

2. For the *source IP* enter **10.8.0.10** and for the *destination IP* enter **10.4.0.10**. Click **Run route analysis**.
    ![Global Network Route Setup](../images/network-manager-route-setup.png)

3. Once the route has analyzed you will be able to see all the hops the traffic will pass through to reach the device.
    ![Global Network Route](../images/network-manager-route.png)
    
4. If we repeat this with following values:
   Source Transit Gateway attachment: NP1Attach
   Source IP: 10.16.0.10
   Destination Transit Gateway attachment: P1Attach
   Destination IP: 10.8.0.10

   We can see the traffic gets blackholed as we saw earlier.
   ![Global Network Route](../images/network-manager-route-block.png)
