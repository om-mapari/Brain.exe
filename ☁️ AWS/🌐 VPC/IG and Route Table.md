
By default subnet follow the main route table
till you create custom route table -\> then subnet follow the coustom route table

Internet Gateway -\> to route traffic to internet

Requirement of Ec2 instance to route public traffic?
\> There should be internet gateway
\> Route table must have entry
| Dest: 0.0.0.0/0 | target: Internet Gateway |
|-----------------|--------------------------|
\> Instance should have public Ip

![image1](../images/054a6fa6c40c4c5685570247cfe8594f.png)

![image2](../images/82b21179d3b343ad97c1305525e6bb5c.png)

![image3](../images/f9a917c127f3426e9562ca74a5e5ba08.png)

![image4](../images/1022fb1bb317420da64d4b6192e08548.png)

![image5](../images/0b40e8cc008c49f7a80575831fc5d128.png)

![image6](../images/0c80e00f6fcc41faadbaa45750f93647.png)

