# VM-task-3
AWS VPC Setup with Public and Private Subnets

This repository contains the steps and configuration for creating a **Virtual Private Cloud (VPC)** in AWS with **public and private subnets**, demonstrating secure cloud network architecture and controlled internet access.

**Objective:**  
- Learn cloud network segmentation  
- Understand public and private subnet separation  
- Gain practical experience with **VPC, subnets, route tables, and internet gateways**  

---

## AWS Resources Created
| Resource | Name/ID | CIDR | Notes |
|----------|---------|------|-------|
| VPC | MyVPC | 10.0.0.0/16 | Main private cloud network |
| Public Subnet | PublicSubnet | 10.0.1.0/24 | Auto-assign public IP, internet access enabled |
| Private Subnet | PrivateSubnet | 10.0.2.0/24 | No public IP, isolated |
| Internet Gateway | MyIGW | - | Attached to VPC for public subnet internet access |
| Route Tables | PublicRouteTable | 0.0.0.0/0 → IGW | Associated with PublicSubnet |
| Route Tables | PrivateRouteTable | - | Associated with PrivateSubnet, no internet route |

---

## Steps to Create VPC with Subnets

1. **Login to AWS Console**  
   - Select your preferred region (e.g., Mumbai `ap-south-1`).  
   - Open **VPC Dashboard**.

2. **Create VPC**  
   - Name: `MyVPC`  
   - IPv4 CIDR: `10.0.0.0/16`  

3. **Create Subnets**  
   - **PublicSubnet:** 10.0.1.0/24, auto-assign public IP enabled  
   - **PrivateSubnet:** 10.0.2.0/24, auto-assign public IP disabled  

4. **Create and Attach Internet Gateway (IGW)**  
   - Name: `MyIGW`  
   - Attach to `MyVPC`  

5. **Configure Route Tables**  
   - PublicRouteTable: 0.0.0.0/0 → IGW, associate with `PublicSubnet`  
   - PrivateRouteTable: no internet route, associate with `PrivateSubnet`  

6. **Launch EC2 Instances for Testing (Optional)**  
   - PublicSubnet instance: Internet accessible  
   - PrivateSubnet instance: No internet access  

---

## Verification
- Public subnet EC2 can access the internet (ping Google, browse web).  
- Private subnet EC2 remains isolated.  
- Route tables and IGW configuration verified in AWS console.  

---

## Cleanup
- Terminate all EC2 instances  
- Detach and delete IGW  
- Delete custom route tables  
- Delete subnets  
- Delete VPC  

> Following this order ensures no accidental billing.

---

## Screenshots
Include screenshots in `/screenshots` folder:
- VPC Dashboard  
- Subnets List  
- Route Tables  
- IGW attached  

---

## Outcome
- Understand cloud network segmentation  
- Separate public and private resources  
- Configure internet access securely  
