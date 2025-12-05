
🛠️ ASG Setup: Step-by-Step Guide

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>📝 Step 1: Choose Launch Template or Configuration</p>
<p>  • Provide a name for your ASG.</p>
<p>  • Choose an existing Launch Template or Launch Configuration.<br />
<br />
</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>🗂️ Step 2: Choose Instance Launch Options</p>
<p>  • Select VPC and Subnets where your instances will launch.</p>
<p>  • Optional: Override launch template.<br />
<br />
</p></td>
</tr>
<tr class="even">
<td><p>🔗 Step 3 (Optional): Integrate with Other Services</p>
<p>  • Attach ASG to an ALB to distribute traffic.</p>
<p></p>
<p>✔ Enable Health Checks:</p>
<p>   ○ EC2 ELB EBS health status.</p>
<p></p>
<p>📌 Best Practice – Health Check Grace Period</p>
<p>  • Set it equal to the average time your app takes to be ready to serve traffic.</p>
<p>    ✅ Grace Period = App Initialization Time</p>
<p>    ○ Example: 300 seconds.</p>
<p>    ○ During this time: ✔ ASG waits before taking action on failing health checks</p>
<p></p>
<p>  ✔ Why it's needed:</p>
<blockquote>
<p>if the instance runs a startup script (user data)</p>
</blockquote>
<p>that installs software or starts services, it won’t be ready immediately.</p>
<p> </p>
<p>  ⚠️ Exception: If instance is stopped/terminated,</p>
<p>ASG replaces it immediately—even during grace period.<br />
<br />
</p></td>
</tr>
<tr class="odd">
<td><p>📈 Step 4 (Optional): Configure Group Size and Scaling</p>
<p>  • Desired Capacity: Number of instances to maintain.</p>
<p>  • Set Minimum and Maximum Capacity limits.</p>
<p>  • Scaling Policies:</p>
<p>    ○ Target Tracking Scaling: Maintain a metric (e.g., average CPU).<br />
<br />
</p>
<p>📊 Average CPU Utilization (How it Works)</p>
<blockquote>
<p>🔍 Formula: Average CPU Utilization = ∑ CPU of InService Instances / N</p>
<p>🔑 Only includes InService instances after warm-up.</p>
<p>🔍 Excludes instances still warming up.</p>
</blockquote>
<p>  📌 Example:</p>
<table>
<colgroup>
<col style="width: 39%" />
<col style="width: 60%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Used for Avg: i-001, i-002, i-003<br />
Avg CPU = (60 + 70 + 40) / 3 = 56.67%</p>
<p></p>
<p>💡If target is 50%, ASG will scale out (add instance).</p></th>
<th><table>
<colgroup>
<col style="width: 31%" />
<col style="width: 29%" />
<col style="width: 38%" />
</colgroup>
<thead>
<tr class="header">
<th>Instance ID</th>
<th>CPU Usage </th>
<th>Warm-up Complete?</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>i-001 </td>
<td>60% ✅</td>
<td>Yes</td>
</tr>
<tr class="even">
<td>i-002 </td>
<td>70% ✅</td>
<td>Yes</td>
</tr>
<tr class="odd">
<td>i-003 </td>
<td>40% ✅</td>
<td>Yes</td>
</tr>
<tr class="even">
<td>i-004 </td>
<td>90% ❌</td>
<td>No</td>
</tr>
</tbody>
</table></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<blockquote>
<p></p>
</blockquote>
<p></p>
<p>🧩 Behind the Scenes</p>
<p>  • CloudWatch collects metrics every 1 min (detailed) or 5 mins (standard).</p>
<p>  • Once the Target Tracking Went (In Alarm) - then scale out</p>
<p>Scale out Alarm - TargetTracking-demo-asg-AlarmHigh</p>
<p>Scale in Alarm - TargetTracking-demo-asg-AlarmLow</p>
<p></p>
<p>🕒 Instance Warm-up Explained</p>
<p>  📍 Purpose: Prevent new instances from affecting scaling metrics (e.g., CPU) until ready.</p>
<p>  • ASG sees average CPU &gt; target → decides to scale out.</p>
<p>  • New instance excluded from average until warm-up completes.</p>
<p> </p>
<blockquote>
<p>⚠️ During warm-up:</p>
</blockquote>
<p>    ○ ASG still sees high CPU → may launch more instances.</p>
<p> </p>
<blockquote>
<p>📌 Set warm-up properly to prevent unnecessary scale-outs.</p>
</blockquote>
<p>  ✅ Warm-Up Time = Grace Period + Load Ready Buffer (~10-30s)</p>
<p></p>
<p>🔒 Scale-In Protection</p>
<p>  📌 Prevents specific instances from being terminated during scale-in.</p>
<p>  ✔ ASG skips protected instances when reducing capacity.<br />
<br />
TODO: Instance maintenance policy</p></td>
</tr>
<tr class="even">
<td><p>🔔 Step 5 (Optional): Add Notifications</p>
<p>  • Use Amazon SNS to get alerts of:</p>
<p>    ○ Instance Launch</p>
<p>    ○ Instance Termination</p>
<p>    ○ ⚠️ Failed Scaling Activities</p></td>
</tr>
<tr class="odd">
<td><p>🏷️ Step 6 (Optional): Add Tags</p>
<p>  • Assign Tags &amp; Enable tag propagation to launched instances.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>🏁 Step 7: Review</p>
<p>  • Review all settings.<br />
</p></td>
</tr>
</tbody>
</table>

If you dont use LB with ASG -- then if you just directly increase stress on 1 instance it ASG will launch another instance

Understanding:
ASG is connected to instances directly via policy
It don't have any connection with LB.. LB does it job Load balancing

ASG job is just to check the CPU Utlization and create the instances

![image1](../images/88782a3f70b64b61ab9e9fcabc400332.png)

