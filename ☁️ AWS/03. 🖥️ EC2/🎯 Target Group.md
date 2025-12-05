
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🔑 What is a Target Group?</p>
<p></p>
<p>Target Group is a logical grouping of EC2, IP or Lambda that receive traffic from a LBs.</p>
<p>  • It tells the Load Balancer where to route traffic.</p>
<p> </p>
<p></p>
<p>📌 Target Group Types (Based on Load Balancer)</p>
<p></p>
<table>
<colgroup>
<col style="width: 49%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Load Balancer Type </th>
<th>Supported Target Types</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>ALB</td>
<td>EC2 , IP , Lambda</td>
</tr>
<tr class="even">
<td>NLB</td>
<td>EC2 , IP , ALBs</td>
</tr>
<tr class="odd">
<td>GWLB  </td>
<td>EC2 , IP</td>
</tr>
</tbody>
</table>
<p></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>🛠️ Auto Scaling Group (ASG) Integration</p>
<p> </p>
<p>✔ If ASG is linked to a Target Group:</p>
<p>  • Instances launched by ASG are automatically registered/deregistered</p>
<p>  • ASG uses Target Group health checks to detect and replace unhealthy instances<br />
</p></td>
</tr>
<tr class="even">
<td><p>📌 Health Checks in Target Groups</p>
<p></p>
<p>🔍 Purpose:</p>
<p>  • Monitors the health of targets to ensure traffic is only routed to healthy instances</p>
<p></p>
<p>⚙️ Key Configurations Example:</p>
<p>  • Protocol: HTTP (HTTP, HTTPS, or TCP)</p>
<p>  • Port: 8080 (Target port)</p>
<p>  • Path: /health (Used with HTTP/HTTPS)</p>
<p>  • Healthy Threshold: 3 (Successful checks to mark as healthy default: 5)</p>
<p>  • Unhealthy Threshold: 2 (Failed checks to mark as unhealthy default: 2)</p>
<p>  • Timeout: 5s (Wait time for a response default: 5s)</p>
<p>  • Interval: 30s (Time between health checks default: 30s)</p>
<p>  • Success Codes: 200</p>
<p> </p>
<blockquote>
<p>✅ Interpretation:</p>
</blockquote>
<p>    • Load Balancer sends a GET /health request to each target every 30s</p>
<p>    • If it receives 3 consecutive 200 OK responses, the target is marked healthy</p>
<p>    • If it fails 2 times in a row, the target is marked unhealthy</p></td>
</tr>
</tbody>
</table>
