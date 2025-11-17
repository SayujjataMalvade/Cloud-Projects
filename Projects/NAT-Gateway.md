#  NAT Gateway – Theory & Practical Guide

#  1. Introduction to NAT Gateway

A NAT Gateway (Network Address Translation Gateway) is an AWS-managed network service that allows instances in a private subnet to connect to the internet while preventing the internet from initiating connections to those instances.

# 2. Why NAT Gateway?

Private EC2 instances require updates, patches, package installation, etc., which often need internet access.
A NAT Gateway solves this problem securely:

* Allows outbound internet traffic from private subnet

* Blocks inbound internet traffic to private subnet

* Fully managed & scalable

* High availability in an AZ

# 3. Components Required

To deploy a NAT Gateway, you need:

* A VPC

* A Public Subnet (with Internet Gateway attached)

* A Private Subnet

* A Route Table for the private subnet

* An Elastic IP (EIP)

* A NAT Gateway

# 5. Step-By-Step Practical – Create NAT Gateway
## Step 1: Create/Use a VPC

* Go to AWS Console → VPC Dashboard

* Click Create VPC

* Select VPC only

  Provide:

* Name: MyVPC

* CIDR: 10.0.0.0/16

## Step 2: Create Two Subnets

* Public Subnet – 10.0.1.0/24
* Private Subnet – 10.0.2.0/24

## Step 3: Attach an Internet Gateway

* Go to Internet Gateways → Create Internet Gateway

* Name it: MyIGW

* Attach to MyVPC

## Step 4: Create a NAT Gateway

* Go to NAT Gateways → Create NAT Gateway

  Select:

* Subnet: Public Subnet

* Elastic IP: Allocate new EIP

* Click Create NAT Gateway

## Step 5: Update Route Table for Private Subnet

* Go to Route Tables

* Select Private Route Table

* Add the route:

  Destination         	Target
  0.0.0.0/0          NAT Gateway


## Step 6: Launch an EC2 Instance in the Private Subnet

* Launch a Linux instance

* Put it in the Private Subnet

* Ensure No Public IP is assigned

## Step 7: Test Internet Access from Private EC2

1.SSH into the private instance using:

* Bastion Host (if you set one up), or

* SSM Session Manager

2.Run:

    ping google.com
    sudo yum update -y


1. NAT Gateway Architecture

     ![NAT Gateway Architecture](https://user-images.githubusercontent.com/24816990/71585599-76776600-2b17-11ea-970d-23401c6c32f5.png)

2. NAT-Gateway Creation Video

    ![VPC Creation Diagram](https://user-images.githubusercontent.com/24816990/71599161-fa4a4600-2b49-11ea-9eab-3f142338605e.gif)



  


