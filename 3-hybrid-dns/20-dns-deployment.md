# DNS Deployment


Run the CloudFormation template 3.tgw-dns.yaml to deploy the Bind server in the DataCenter VPC as well as the remaining AWS Route53 components

</br>

<b>HOW TO Deploy the Bind Server</b></br>


1. Click on the CloudFormation Launch link below that corresponds to the AWS Region in which you deployed the first stack:

   [![US East (N. Virginia)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)
   [![US East (Ohio)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)
   [![US West (Oregon)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-west-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)
   [![EU West (Ireland)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-west-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)
   [![EU West (Singapore)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-southeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)
   [![AP Northeast(Tokyo)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-northeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-northeast-1#/stacks/create/review?stackName=tgw1-dns&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/3.tgw-dns.yaml&param_VPCName=tgw1&param_Zone=example.com)

1. Give the stack a name, enter the name of your first stack (must be entered accurately) and select a DNS compliant domain name, such as **kneetoe.com**. Click **Next**.
   ![Stack Parameters](../images/createStack-DNSparameters.png)

1. For **Configuration stack options** we don't need to change anything, so just click **Next** at the bottom right.

1. Scroll down to the bottom of the **Review name_of_your_stack** and check the **I acknowledge that AWS CloudFormation might create IAM resources with custom names.** Click the **Create** button in the lower right.
   ![Create Stack](../images/createStack-VPCiam.png)

1. Wait for the Stack to show **Create_Complete**.
   ![Stack Complete](../images/createStack-DNSprogress.png)