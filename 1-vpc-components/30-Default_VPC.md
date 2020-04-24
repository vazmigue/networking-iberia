# Deleting the Default VPC

A default VPC is automatically created for each region in your account. Some customers choose to remove the default VPC and replace it with one or more that they have planned out to keep things simple and secure. We are going to remove the default VPC for another reason: the maximum number of VPCs per region in an account is five (although that's a soft limit) and our Lab uses five VPCs. If you require more than five in your own accounts, it's easy to increase them by making a limit request through the support console, while logged into your account: https://console.aws.amazon.com/support/cases#/create.


_Note: if you decide to remove your default VPC in your own account, you can always recreate it via the console or the CLI. See the [documentation](https://docs.aws.amazon.com/vpc/latest/userguide/default-vpc.html#create-default-vpc "AWS Default VPC Documentation")._

1. In the AWS Management Console change to the Region you plan to work in. This Region selection is in the upper right-hand drop-down menu.

2. In the AWS Management Console choose **Services** then select **VPC**.

3. From the left-hand menu select **Your VPCs**.

4. In the main panel, the checkbox next to only VPC (the default VPC) should be highlighted. You can verify this is the default VPC by scrolling to the right. The _Default VPC_ column will be maked with **Yes**.

5. With our default VPC checked select the **Actions** dropdown above it and select **Delete VPC**.

6. In the **Delete VPC** Panel, check the box 'I Acknowledge that I want to delete my default VPC.' and click the **Delete VPC** button in the bottom right.

7. You should get a green highlighted dialog stating 'The VPC was deleted' and you can click **Close**. _If it is red, then likely something is deployed into this VPC and you will have to remove those resources (items such as EC2 instances, NAT Gateway, VPC endpoints, etc., all of which would prevent your VPC from deleting). You could also consider another Region from the list above._
