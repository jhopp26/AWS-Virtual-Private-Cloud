# AWS-Virtual-Private-Cloud

## Objective

The goal of this project was to create a secure and scalable network infrastructure in Amazon Web Services (AWS) by setting up a custom Virtual Private Cloud (VPC) along with its associated components, such as subnets, route tables, and Network Access Control Lists (NACLs). Additionally, the project aimed to configure these components to ensure proper network segmentation, access control, and internet connectivity while adhering to security best practices. 

### Skills Learned
- Understanding AWS fundamentals of a Virtual Private Cloud (VPC) and its components.
- Configuring networking components within AWS, such as creating custom VPCs, setting up internet gateways, and configuring subnets.
- Configuring route tables to direct traffic within the VPC, including setting up appropriate routes for both public and private subnets.
- Implementing security measures within AWS, including creating Network Access Control Lists (NACLs) and configuring inbound and outbound rules to control traffic flow and enhance network security.
- Deploying EC2 instances within both public and private subnets, including generating key pairs for secure access and connecting to instances using Remote Desktop Protocol (RDP).

### Tools Used

- AWS Management Console
- AWS Command Line Interface (CLI)
- AWS Virtual Private Cloud
- Subnets
- Routing Tables
- Secuirty Groups
- Network Access Control Lists (NACL)

## Project Walk-Through

### Goal of project

![Goal of Project](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/f64b86e4-9f11-4c78-97b7-13d17c2db797)

### Step 1
Create VPC and internet gateway and attach them to each other

![Step 1 - Create VPC](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/3e8b0b10-c342-4537-92c9-bfdc2822e69b)

![Step 2 - Create IGW](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/861d68b1-f09c-4e5e-b7b9-5d35e552366f)

![Step 2a - Attach IGW](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/6b832d7d-2faf-4b7e-94ff-a4918f0edd90)

### Step 2
Create public and private subnet within VPC

![Step 4 - Create Public RT](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/7a40f589-4881-4170-b6e4-72f8f418724a)

![Step 4a - Private RT](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/e53f520d-9599-4bc4-8be8-073a3f766291)

### Step 3
Configure routing tables and assiocate them to public and private subnet 

![Step 5 - Edit Route Table for Public RT](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/b6a19a74-b67b-4a66-a02a-a1b6af695aee)

![Step 5a - Associate Public Subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/bc1ca892-4eea-449c-9eb0-3097100ce6ef)

![Step 6 - Keep Private Subnet Default](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/36bf3fc5-14a2-4930-b516-2a1790b7b5e2)

![Step 6a - Assoicated with Private Subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/70d91c88-8de5-4960-ade4-bba73003b62a)

### Step 4
Implement a NACL to each subnet and assiocated them to the right subnet. I configured the public NACL to allow any inbound and outbound HTTP traffic and configured only local inbound traffic for the private

![Step 7 - Create Public Network ACL](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/5d759b22-929f-42dc-9b2b-dfbf14e097a2)

![Step 7a - Edit Inbound Rules](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/90796122-499f-4c92-b65b-8609f0eb5744)

![Step 7b - Edit Outbound rules](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/6b9fa04a-f039-4de7-be80-fee3ef099d87)

![Step 7c - assoicate public subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/56ff0ed5-e52d-4090-a5d3-bd75d5656933)

![Step 8 - Create Private Network ACL](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/4013a973-aa8c-4abc-bbc8-12abd7664edd)

![Step 8a - Edit Inbound rules for Private NACL](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/6d27ed73-0cb8-483f-ac60-651565642485)

![Step 8b - Edit outbound rules for private NACL](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/f96abd67-a0cd-47ab-9651-77b4f0a9011b)

![Step 8c - assiocate private subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/e540d609-564f-4780-9bb0-870e1ba135d5)

### Step 5
Launched an EC2 instance, configured network settings to include the VPC and public subnet, and utilized a key pair to establish a Remote Desktop Connection for secure access.

![Step 9 - Creste EC2 via Windows   T2 Micro](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/d8fcad39-04e0-4e84-955c-26ef1a02e1ef)

![Step 9 - SuccessFul EC2](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/23200462-0001-41ab-990f-0c6f105c6f2d)

![Step 9a - Configure EC2](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/6a1c64f8-9b58-4311-9de3-2561320f4f96)

![Step 9b - Create Security Group and Key Pair](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/f6235a69-252e-4731-a704-7dfecc7b3d4a)

![Step 10 - Successful Connection to Public Subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/c850ac9d-1a63-4667-8588-dad95b560cbe)

### Step 6
Deployed another EC2 instance, configured network settings to include the VPC and private subnet, and used a key pair to securely access the private EC2 instance via Remote Desktop Connection while located within the public subnet.

![Step 11 - Create Private EC2 with window and T2 micro](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/30f2d8c1-01a7-4795-a0ac-a8c235decadb)

![Step 11a - Set Security Group Inbound to only Public Subnet](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/510c440c-52ed-47d2-be7b-8755c4fc737f)

![Step 12 - Successful Public and Private Connection](https://github.com/jhopp26/AWS-Virtual-Private-Cloud/assets/166570789/32b6505c-3a5b-498b-87a3-7020d84d35be)



