
✅ VPC Setup with Public & Private Subnets, NAT Gateway, and IGW

![image1](../../images/4c259afd4a3f4820ad5d3ac00216abc0.png)

🔧 VPC & Subnet Creation
• Create a VPC
  ○ CIDR block: 11.0.0.0/16
• Create Subnets
  ○ Public Subnet: 11.0.1.0/24
  ○ Private Subnet: 11.0.2.0/24
  ○ Ensure subnets are in the same Availability Zone as the NAT Gateway
(for simplicity)

![image2](../../images/04ae9538c8ef482d8e4980d51abc0243.png)

🌐 Create and Attach Internet Gateway (IGW)
• Create IGW
  ○ Attach the IGW to your VPC
  ○ Required for public resources to access the internet

![image3](../../images/692f8ee6f7f64162a5545c65c4d2c631.png)

📜 Create and Associate Route Tables
• Create 2 Route Tables
  ○ One for Public Subnet
  ○ One for Private Subnet

![image4](../../images/138d48b28a7e406f988b843be208782a.png)

• Associate Route Tables to Subnets
  ○ Public Route Table → Public Subnet
  ○ Private Route Table → Private Subnet

![image5](../../images/cc190d1284384ef39bf64c8cd5a811a7.png)

🌍 Update Public Route Table
• Add route to public route table:
  ○ Destination: 0.0.0.0/0
  ○ Target: Internet Gateway

![image6](../../images/d7ed14ac60a44486a93c4d3359d30cf8.png)

⚙️ Create and Configure NAT Gateway
• Create NAT Gateway
  ○ Must be in Public Subnet
  ○ Requires Elastic IP
  ○ NAT Gateway is used by private instances for outbound internet access

![image7](../../images/72a6d4393203434b8cba894c422bd0f2.png)

• Important Notes
  ○ NAT Gateway is not used for inbound traffic
  ○ It is expensive (hourly + data usage)
  ○ It allows private subnet to reach internet for updates, downloads, etc.
○ Acts as Proxy for Private Ec2 instance

📦 Update Private Route Table
• Add route to private route table:
  ○ Destination: 0.0.0.0/0
  ○ Target: NAT Gateway

![image8](../../images/9c2f207110484f1cb929ba48fdb2306e.png)

🖥️ Launch EC2 Instances
• Launch Public EC2 Instance
  ○ Subnet: Public
  ○ Auto-assign Public IP: ✅ Yes
• Launch Private EC2 Instance
  ○ Subnet: Private
  ○ Auto-assign Public IP: ❌ No

![image9](../../images/2bb3f4ba6fa445dfb19a49cb6e874bb0.png)

🔐 Security Groups Configuration
• Public EC2 SG
  ○ Inbound: Allow SSH (port 22) from your IP address
• Private EC2 SG
  ○ Inbound: Allow SSH from Public EC2's private IP or CIDR 11.0.1.0/24
• Tip
  ○ Follow the Principle of Least Privilege — allow only what's needed

![image10](../../images/107db30b02c04c0b8468ae1a47d0a13d.png)

🔗 SSH into Private EC2
• SSH into Public EC2 from your local machine:
  ○ Use the public IP and .pem key

![image11](../../images/befc70fcbc964b6ea1859e988e4ec2db.png)

![image12](../../images/42b159f6cb5a414c8fd4e935dcd674ca.png)

• SSH into Private EC2 from inside Public EC2:
  ○ Use private IP of the private EC2 and the same .pem key
• This is known as a Bastion Host (Jump Box) setup

• Run: curl ipinfo.io
  ○ It shows the Elastic IP of the NAT Gateway, confirming NAT works

![image9](../../images/2bb3f4ba6fa445dfb19a49cb6e874bb0.png)

![image13](../../images/e82dd374a8484e1f88b420ba23f9f6fb.png)

![image14](../../images/41e98db949674f639c6dc15ee6237854.png)

IMP: EC2 stays private (Uses NAT IP Proof)

![image15](../../images/f9ee691b8c0148c7b9d75d72acb4ce09.png)

🌐 Internet Access Behavior
• Public EC2
  ○ Has both private and public IP
  ○ Uses IGW for internet access
• Private EC2
  ○ Has only private IP
  ○ Uses NAT Gateway in public subnet for outbound-only internet access
  ○ Cannot be reached from internet directly

🔁 IGW vs NAT Gateway
| Feature | Internet Gateway (IGW)  | NAT Gateway (NAT GW) |
|----|----|----|
| Used | In Public Subnets  | Private Subnets |
| Internet | Access Inbound + Outbound  | Outbound only |
| IP Needed  | No  | Yes (Elastic IP) |
| Cost   | Free   | Paid |
| Accept Incoming Conn.  | Yes | No |
| Public IP Req.  | EC2 needs Public IP | EC2 stays private (uses NAT IP) |

🧠 Must-Know Concepts
• Elastic IP
  ○ A static public IP in AWS, used with NAT Gateways or EC2
• Bastion Host ( Jump Server )
  ○ Public instance used to SSH into private instances
• Security Group vs NACL
  ○ SG is stateful (response traffic allowed automatically)
  ○ NACL is stateless (explicit rules for both inbound and outbound)

![image16](../../images/d3e6b1f6f3fc4847b2268972e59930f2.png)

⚠️ Best Practices
• Avoid giving private EC2 a public IP
• Restrict SSH access using security groups
• Monitor NAT Gateway usage to manage costs
• Use NAT Instance (EC2-based) for cheaper alternative (but less scalable)

