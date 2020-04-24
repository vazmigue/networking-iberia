# VPCs - Deployment


We need to get our infrastructure in place. The following CloudFormation template will build out _five_ VPCs. Pick the region you want to and keep that choice during any lab.

As noted earlier in the lab, this is what the VPCs look like:

- Three VPCs for our Development, Test, and Production environments (one VPC each).
- One VPC for our Shared Services, such as VPC Endpoints, Hybrid DNS and NAT Gateway.
- One VPC emulating our Datacenter.


Click on the CloudFormation Launch link below that corresponds to the AWS Region in which you want to deploy the workshop.</br> 
_Note: if you are sharing the AWS account with someone else be sure to pick different regions._

   [![US East (N. Virginia)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=us-east-1a&param_AvailabilityZoneB=us-east-1b)
   [![US East (Ohio)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-east-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-east-2#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=us-east-2a&param_AvailabilityZoneB=us-east-2b)
   [![US West (Oregon)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/us-west-2.svg)](https://console.aws.amazon.com/cloudformation/home?region=us-west-2#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=us-west-2a&param_AvailabilityZoneB=us-west-2b)
   [![EU West (Ireland)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/eu-west-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=eu-west-1#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=eu-west-1a&param_AvailabilityZoneB=eu-west-1b)
   [![EU West (Singapore)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-southeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-southeast-1#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=ap-southeast-1a&param_AvailabilityZoneB=ap-southeast-1b)
   [![AP Northeast (Tokyo)](https://samdengler.github.io/cloudformation-launch-stack-button-svg/images/ap-northeast-1.svg)](https://console.aws.amazon.com/cloudformation/home?region=ap-northeast-1#/stacks/create/review?stackName=tgw&templateURL=https://s3.amazonaws.com/{{<codebucket>}}/1.tgw-vpcs.yaml&param_AvailabilityZoneA=ap-northeast-1a&param_AvailabilityZoneB=ap-northeast-1c)

1. If you are sharing the account with someone else doing the workshop, add your initals to the **Stack name**. This will make any IAM roles or other global resources unique.

2. Scroll down to the bottom of the **Review name_of_your_stack** and check the **I acknowledge that AWS CloudFormation might create IAM resources with custom names.** Click the **Create** button in the lower right.
   ![Create Stack](../images/createStack-VPCiam.png)

3. Wait for the Stacks to show **Create_Complete**. A couple of stacks will be deployed:
   ![Stack Complete](../images/createStack-VPCComplete.png)



