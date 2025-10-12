
📘 Types of IP Addresses in EC2

| Type             | Scope    | Static? | Charges? | Use Case                       |
|------------------|----------|---------|----------|--------------------------------|
| Private IP       | Internal | ✔ Yes   | ❌ No    | Internal VPC communication     |
| Public IP        | Internet | ❌ No   | ❌ No    | Quick internet access          |
| Elastic IP (EIP) | Internet | ✔ Yes   | ⚠️ Yes   | Static access, failover setups |
| IPv6             | Internet | ✔ Yes   | ❌ No    | Global routing, IPv6 access    |

![image1](../../images/fcecdf85010c4a6a865339f3142bbbec.png)

How to connect
\- ssh -i mypem.pem aws-user@hostname
\- SG must have ssh inbound Rule

How to check Public IP? ( AutoAssigned or EIP )
\- 3.7.70.216\[ec2-user@ip-172-31-7-13 ~\]\$ curl ipinfo.io

  {
  "ip": "3.7.70.216",
  "hostname": "ec2-3-7-70-216.ap-south-1.compute.amazonaws.com",
  "city": "Mumbai",
  "region": "Maharashtra",
  "country": "IN",
  "loc": "19.0728,72.8826",
  "org": "AS16509 Amazon.com, Inc.",
  "postal": "400017",
  "timezone": "Asia/Kolkata",
  "readme": "<https://ipinfo.io/missingauth>"
  }

How to check Private IP?
  ifconfig
  or
  \[ec2-user@ip-172-31-7-13 ~\]\$ hostname -I
  172.31.7.13
