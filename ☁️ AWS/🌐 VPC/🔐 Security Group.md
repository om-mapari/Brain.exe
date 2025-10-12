
![image1](../images/0049cde26aa34b7d86ab8c08fa495eca.png)

![image2](../images/2d56076b82b247239a21e2a5c3e1a619.png)

![image3](../images/125785180bea41af829cbd4896868c98.png)

If your EC2 makes a valid outbound request, the **response is automatically allowed back in**, even if your **inbound rules are empty**.

If EC2 is in a public subnet with internet access → ✅ You’ll get a JSON response.
If EC2 is in a private subnet with no NAT → ❌ The request will hang or fail.

Inboud Rule

from 1 machine
![image4](../images/45665a4035b7443f9952383fea62504a.png)

from anywhere ssh allowed
![image5](../images/73b491e748aa47b1b2f525d28ddde8b0.png)

Outbound Rule:

In Amazon EC2 Security Groups (SGs), the default outbound rule for a new security group is:
Allow all outbound traffic (0.0.0.0/0 for IPv4 and ::/0 for IPv6) on all protocols and all ports.

Even if you remove default outbound:
✅ Your EC2 will still respond to incoming requests — like a browser request from your PC — because Security Groups are stateful.

![image6](../images/cfbe5176f0264b249e9ec427e4916e54.png)

![image7](../images/08afcfb0d95a47098acad58eafa009b1.png)

EC2 - EC2 Communication
![image8](../images/cdf8c54ac7ea4c0ebedbcae7c5be16a5.png)

Only from the web servers :)

![image9](../images/72d3bc834eb446ea830971c366a214c8.png)

![image10](../images/f5fedbad41b244dd86e93cc625747856.png)

![image11](../images/30075cb8b26b445cb1b2b417f8e03d1f.png)

---------------------------------------------

Default security group

self reference in it's inbound rule
\- All machine that are attach to it can talk to each other

![image12](../images/bc250e208c6945d4966b451160713f37.png)

![image13](../images/78650d5379de4f55828c99afb8c78911.png)

![image14](../images/d9c5db38577a4601b6dc901f6356f5ab.png)

