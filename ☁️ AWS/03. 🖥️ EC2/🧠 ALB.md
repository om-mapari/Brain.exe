
🧠 AWS ALB (Application Load Balancer)

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p>
<p>🔍 What is ALB?</p>
<p>• Application-layer (Layer 7) load balancer in ELB family</p>
<p>• Handles HTTP/HTTPS traffic</p>
<p>• Supports content-based routing, SSL termination, and WebSocket<br />
<br />
While Creating:</p>
<p>Launch it in Public AZ for internet facing</p>
<p>AllowHTTP Port 80 in SG of ALB<br />
<br />
</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>🔧 Core Components</p>
<p></p>
<p>1) 📡Listener</p>
<p>• Defines protocol and port (e.g., HTTP:80, HTTPS:443)</p>
<p>• that the ALB uses to listen for incoming traffic.</p>
<p></p>
<p>• For HTTPS, must define SSL/TLS certificate</p>
<p>  ○ ALB can decrypt SSL → reduces backend load</p>
<p>  ○ Works with AWS ACM (free certs)</p>
<p>  ✔ Best Practices</p>
<p>    ○ Terminate SSL at ALB for centralized cert management</p>
<p>    ○ Boosts performance by offloading resource-intensive SSL task</p>
<p></p>
<p>2) 🎯 Target Groups (<a href="onenote:#🎯%20Target%20Group&amp;section-id={2A2C6C0B-4FB4-4574-B5DF-19755D1A951A}&amp;page-id={8E314693-AD62-41F5-894E-5AD7453608DC}&amp;end&amp;base-path=https://d.docs.live.net/488D82FE7A9FEF0F/Documents/AWS/🖥️%20EC2.one">Target Groups</a>)</p>
<p>• Collections of targets (e.g., EC2, Lambda, IP)</p>
<p>• That Receive traffic based on listener rules</p>
<p>• Health checks defined at TG level</p>
<p></p>
<p></p>
<p>3) 🛣 Listener Rules</p>
<p>• Rules are Used to Route traffic to TG based on the if condition on each request of listner</p>
<p></p>
<p> ○ If Conditions:</p>
<p>    ✔ Path-based → /api → API service</p>
<p>    ✔ Host-based → admin.site.com → Admin service</p>
<p>    ✔ Header-based → based on HTTP headers</p>
<p>    ✔ Use Weighted Target Routing when multiple TGs are used</p>
<p></p>
<p>  ○ then: Action FW 30% trffic to TG | Redirect to URL | Return Fixed Response</p>
<p></p>
<p></p>
<blockquote>
<p>![image1](../images/c0142e7d11f4475ab71321778b036643.png)</p>
</blockquote>
<p></p>
<p></p>
<p>• 📌 Rule Types:</p>
<p>  ○ Default Rule → used when no custom rule matches</p>
<p>  ○ Custom Rules → evaluated top to bottom</p>
<p>✔ALB rules have unique priorities (1–50,000); lower runs first, default runs last.</p>
<p>✔Use gaps (e.g., 100, 200) for easy future rule additions.</p>
<p></p>
<p></p>
<p>• 💡 Weighted Routing on TG</p>
<p>  ○ weight value is proportional, Use to split traffic across multiple TG.</p>
<p></p>
<table>
<colgroup>
<col style="width: 45%" />
<col style="width: 30%" />
<col style="width: 23%" />
</colgroup>
<thead>
<tr class="header">
<th>Target Group  </th>
<th>If Weight</th>
<th>Traffic</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>tg-blue  </td>
<td>80</td>
<td>80%</td>
</tr>
<tr class="even">
<td>tg-green  </td>
<td>20</td>
<td>20%</td>
</tr>
</tbody>
</table>
<blockquote>
<p></p>
</blockquote>
<p></p>
<p>• 🧷 Turn on target group stickiness</p>
<p>  ○ Enable on a rule to bind user sessions to the same target</p>
<p>  ○ Why: Useful when your app stores session data locally on the instance</p>
<p>(i.e., not in a shared DB or Redis).</p>
<p>  ○ How: Only works if client supports cookie.</p>
<p></p>
<p></p></td>
</tr>
<tr class="even">
<td><p>🛠️ Key Features:</p>
<p></p>
<p>🌐 WebSocket &amp; HTTP/2</p>
<p>  • ALB Supports real-time comms &amp; modern protocols</p>
<p>    ○ Great for chat apps, live updates, etc.</p>
<p></p>
<p>🛡️ AWS WAF Support</p>
<p>  • Add extra security with AWS WAF</p>
<p>    ○ Protects against DDoS, SQLi, XSS</p>
<p></p>
<p>💸 Pricing</p>
<p>  • Charged based on:</p>
<p>    ○ ALB uptime (per hour)</p>
<p>    ○ LCU (Load Balancer Capacity Units)<br />
<br />
<br />
Problem:</p>
<p>  • ALBs don't support static IPs (only a static DNS name), which is problematic for external DNS providers. solve it with NLB -&gt; ALB -&gt; Instance</p>
<p></p>
<p></p></td>
</tr>
</tbody>
</table>
