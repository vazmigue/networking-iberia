# Final Testing

1. In the AWS Management Console choose **Services** then select **Systems Manager**.

1. From the menu on the left, scroll down and select **Session Manager**. Session Manager allows us to use IAM role and policies to determine who has console access without having to manage ssh keys for our instances.

1. In the main pane, click the **Start session** button. Pick the **NP1 Instance** to shell into. You will now enter a bash shell prompt for that instance.

1. Let's try to ping the EC2 instance located within the **NP2 Private Subnet**. You can get the NP2 instance ip from the EC2 section:
	![NP2 instance](../images/np2-private-ip.png)




