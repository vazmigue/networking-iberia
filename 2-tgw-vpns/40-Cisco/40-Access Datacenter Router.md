## Accessing the Cisco CSR router using the AWS Cloud9 Environment

Instead of using a traditional SSH client such as Putty for Windows users or any other Linux alternative, we will be using AWS Cloud9 in order to access the Datacenter router. Cloud 9 is an IDE platform managed as a service. We will be using just a fraction of its capabilities but this intro should give you some ideas about how you can provide a shared environment for managing your infrastructure as a development environment:

1. In the AWS Management Console change to the region you are working on. This is in the upper right hand drop down menu.

2. In the AWS Management Console choose **Services** then select **Cloud9**.

3.From **Your Environments** page click the **Open IDE** button on the Workshop Environment Box.
![Cloud 9 Environments](/images/cloud9-environments.png)

4. This will bring up the Cloud9 Console and download the Github repo to your working folder.

5. From the **file** menu select **Upload Local Files...** and click **Select files** button, navigate to the key file you created earlier. _Note: It should have a .pem extension_. In the Cloud9 console, the file will show up in the left-hand folder list.
   ![Upload file to Cloud9](/images/cloud9-uploadfile.png)

6. In the main panel click the **x** sign next to the **welcome** tab to close this tab.

7. In the main panel click the **+** sign and launch a **New Terminal**. This is a bash shell on the Cloud9 Instance.

8. move the key to the .ssh folder: `mv _key_name_.pem ~/.ssh/`

9. restrict access to the key file: `chmod 400 ~/.ssh/_key_name_.pem`

10.From another browser tab, again navigate to the Management Console and choose **Services** then select **CloudFormation**.

11. From the left-hand menu, select **Exports** in the left hand menu and find the export for ssh to the CSR: DC1-_stack-name_-CSRssh and copy the **Export value**
   ![ssh key and ssh to CSR](/images/cloudformation-csrssh.png)

12. Back on the **Cloud9** Browser tab paste this into the bash shell. _note: in the command you will notice the -i reference to the pem file you just copied, this is the private half of the key pair. The public key is on the Cisco CSR_. Answer **yes** to **Are you sure you want to continue connecting (yes/no)?**

13. You now are connected to the Cisco CSR in the Datacenter VPC. We will be configuring the Cisco CSR.

14. Lets look at the Interfaces by typing a the #prompt: **show ip interface brief** or **sh ip int br** for short. You will see the GigabitEhternet1 which is the interface our ipsec tunnel were traverse.

15. Take a look at the route table on the CSR by typing at the #prompt: **sh ip route**. You will see S\* 0.0.0.0/0 which is a static default route pointing to the 10.4.0.1 address. This is the local VPC router which will connect the Interface to the Internet Gateway and use an Elastic IP address (The Elastic IP will be used as the Customer Gateway IP address when we setup the VPN between the datacenter and the Transit Gateway). The public Elastic IP is a one-to-one mapping to the private 10.4.x.x IP address you just SSHed to.
