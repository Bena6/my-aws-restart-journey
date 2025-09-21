### Introduction
In this project, we'll set up a custom Virtual Private Cloud (VPC) from scratch inside AWS.
Think of a VPC like building your own private city in the cloud — dividing it into neighborhoods (subnets) and linking it to the outside world (internet gateway).

#### You'll learn how to:

Create a VPC

Set up a public subnet

Attach an internet gateway for external connectivity

#### Cost

FREE (Eligible under AWS Free Tier)

#### Objectives

create Amazon VPC

Public Subnet

Internet Gateway

What is a VPC?

A Virtual Private Cloud (VPC) is a private section of AWS where you can launch AWS resources in a logically isolated network.

What is a Subnet?

A subnet is a subdivision within your VPC where you can place resources according to different access rules — like public-facing servers or private databases.

What is an Internet Gateway?

An Internet Gateway connects your private VPC to the broader internet, enabling resources like EC2 instances to communicate externally.

### Step 1: Create a VPC

Log in to the AWS Management Console.

Search for VPC in the search bar.

In the left navigation pane, select Your VPCs.

Click Create VPC.

Choose VPC Only option.

Set:

Name tag: Bena VPC

IPv4 CIDR block: 10.0.0.0/16

Take a screenshot of your setup page.

Click Create VPC. VPC is ready!

### STEP 2. Create a Public Subnet

In the VPC Dashboard, choose Subnets from the left menu.

Click Create Subnet.

Fill:

VPC ID: XYZ VPC

Subnet name: Public 1

Availability Zone: Choose the first AZ available.

IPv4 CIDR block: 10.0.0.0/24

Click Create Subnet.

Enable Auto-Assign Public IP.

Select the checkbox next to Public 1.

Click Actions > Edit subnet settings.

Check Enable auto-assign public IPv4 address.

Save the changes.

Note:
Auto-assigning public IP addresses ensures instances in this subnet can be accessed via the internet.

### STEP 3. Create and Attach an Internet Gateway

In the left menu, click Internet Gateways.

Click Create Internet Gateway.

Set:

Name tag: Bena IG

Click Create Internet Gateway.

Attach the Internet Gateway to VPC:

Select Bena IG.

Click Actions > Attach to VPC.

Choose Bena VPC.

Click Attach Internet Gateway.

Note:
Now, the VPC can communicate with the internet through the attached Internet Gateway.

#### Clean Up:

To avoid any AWS charges:

Detach and delete the Internet Gateway.
Delete the Subnet.
Delete the VPC.
