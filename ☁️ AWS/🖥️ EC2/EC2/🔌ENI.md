
📝 What is an ENI (Elastic Network Interface)?
  • An ENI is a virtual network interface that you can attach to an EC2 instance.
  • It's a logical networking component in a VPC, acting like a virtual NIC (Network Interface Card).
  📌 It enables your EC2 instance to communicate within the VPC and with the internet (if allowed).

🔍 Key Components of an ENI
  • Primary private IPv4 address
  • One or more secondary private IPv4 addresses
  • Elastic IP address (optional)
  • MAC address
  • Security groups
  • Source/destination check flag
  • Attachment to one EC2 instance at a time

💡 Use Cases
  ✔ High Availability
  • You can move an ENI (with its IPs and SGs) between instances, great for failover and automation!

⚙️ ENI Types
  📌 Primary ENI • Created by default when an EC2 instance is launched. Not Detachable
  📌 Secondary ENI • Additional interfaces manually attached to an instance. Only Secondary ENIs are detachable!

🔢 ENI Limits (varies by instance type):
  • t2.micro: 1 ENI
  • Larger types: Up to 15 ENIs

🛠️ ENI CLI Commands
  ✔ Attach ENI to EC2
    aws ec2 attach-network-interface \\
    --network-interface-id eni-xxxxxxxx \\
    --instance-id i-xxxxxxxx \\
    --device-index 1
  ✔ Detach ENI

aws ec2 detach-network-interface \\
 --attachment-id eni-attach-xxxxxxxx
