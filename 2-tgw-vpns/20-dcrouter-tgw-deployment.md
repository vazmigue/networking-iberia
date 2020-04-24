# Datacenter Router and Transit Gateway Deployment


Using a predefined CloudFormation template we will deploy a Cisco Router (Cisco CSR) into the Datacenter VPC simulating our on-premise VPN router.
In addition, a Transit Gateway will be deployed with a couple of Transit Gateway route tables.


1. Click on the CloudFormation Launch link below that corresponds to the AWS Region in which you deployed the first stack:

   [![US East (N. Virginia)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)
   [![US East (Ohio)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)
   [![US West (Oregon)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-west-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)
   [![EU West (Ireland)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-west-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)
   [![EU West (Singapore)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-southeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)
   [![AP Northeast (Tokyo)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-northeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-northeast-1#/stacks/create/review?stackName=tgw-csr&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/2.tgw-csr.yaml&param_ParentStack=tgw)

2. For the **Specify stack details** give the stack a name (compounded names work well. i.e. if the VPC stack created in the first lab was named **TGW1**, name this stack **TGW1-CSR**), pick the keypair you created earlier and enter the name of your first stack (must be entered exactly to work). Also stick with "Cisco" as the router vendor. Click **Next**.
   ![Stack Parameters](../images/createStack-CSRparameters.png)

3. For **Configuration stack options** we don't need to change anything, so just click **Next** in the bottom right.

4. Scroll down to the bottom of the **Review name_of_your_stack** and check the **I acknowledge the AWS CloudFormation might create IAM resources with custom names.** Click the **Create** button in the lower right.
   ![Create Stack](../images/createStack-VPCiam.png)

5. Wait for the Stack to show **Create_Complete**.
   ![Stack Complete](../images/createStack-CSRcomplete.png)