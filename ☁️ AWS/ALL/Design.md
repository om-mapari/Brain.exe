
![image1](../images/51473d70fd5c40faaeddb91671d4ead2.png)

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 79%" />
</colgroup>
<thead>
<tr class="header">
<th><p>DNS = RouteS3</p>
<p></p>
<p>![image2](../images/19ceefe8b766437cb8d75203a04344d2.png)</p>
<p></p></th>
<th><p>- where the traffic come from the internet</p>
<p>- health check</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Load Balencer</p>
<p></p>
<p>![image3](../images/b45af94c3b494394bfbad028bc358569.png)</p></td>
<td><p>- ELB = Elastic load balencer</p>
<p>has 2 veriation</p>
<p>- ALB = application load balencer ( L7 level)<br />
- NLB = network load balencer ( L4 level)<br />
</p>
<p></p>
<p></p>
<p></p></td>
</tr>
<tr class="even">
<td></td>
<td>3 choice for Web Backend layer</td>
</tr>
<tr class="odd">
<td><p>EC2<br />
</p>
<p>![image4](../images/3103778f6c844a9389932a03fac23700.png)</p></td>
<td>- you can run vertual machine</td>
</tr>
<tr class="even">
<td><p>Lambda<br />
</p>
<p>![image5](../images/c7a90dc25ec64f96b91bc11a6737346f.png)</p>
<p></p></td>
<td><p>- serverless<br />
- no need to worry about infra</p>
<p>- pay per invocation</p></td>
</tr>
<tr class="odd">
<td><p>ECS<br />
</p>
<p>![image6](../images/57483d6a96b442d98a349d3ebdf4f4dd.png)</p>
<p></p></td>
<td><p>- middle between EC2 and lambda</p>
<p>-</p></td>
</tr>
<tr class="even">
<td><p>Api Gateway<br />
</p>
<p>![image7](../images/8fad56717f554209ab1ff55b5285b187.png)</p>
<p></p></td>
<td><p>- Api Gateway<br />
- Help to host apis</p>
<p>- Feature - Api throttling</p>
<p>- authorization on an api</p>
<p>Better than ELB</p></td>
</tr>
<tr class="odd">
<td><p>Elastic Cache<br />
</p>
<p>![image8](../images/31f79c5e38f34acf97eb3f8ddda01807.png)</p></td>
<td><p>- 2 flaver</p>
<p>- Memcached based or Redis</p></td>
</tr>
<tr class="even">
<td><p>Aurora</p>
<p>RDS DB</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>DynamoDB<br />
</p>
<p>![image9](../images/fe3513efbc0a4cb9838abcf5ece90b6b.jpeg)</p>
<p></p></td>
<td><p>![image10](../images/368c9461b5094c8c90c70da88877ec2f.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td></td>
<td></td>
</tr>
<tr class="odd">
<td></td>
<td><p>![image11](../images/53ba276325144adcac62ccab6d13c499.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td>Cloud watch</td>
<td>- it has many services<br />
- view diff matrics on ec2 machine what is cpu or memery uutilization<br />
- lambda How many invokation it has<br />
- logging</td>
</tr>
<tr class="odd">
<td>Cloud Trail<br />
<br />
</td>
<td>- Cloud watch help to monitor sate of app<br />
Where as Cloud Trail help to monitor infra<br />
<br />
- who is deleting<br />
- who is accessing what services and what are they doing to the services<br />
</td>
</tr>
<tr class="even">
<td><p>IAM<br />
</p>
<p>![image12](../images/b8cdf0c264c84c8fa39dd8301db978fc.png)</p>
<p></p></td>
<td>Security management service<br />
<br />
We create User or Role<br />
User has policy by default user don't have permission to do anything with aws unless you attach IAM policy to that user</td>
</tr>
<tr class="odd">
<td><p></p>
<p>![image13](../images/02ee2ee1cc50408389e85e6b9967a456.png)</p>
<p></p></td>
<td><p>Event Co-ordination<br />
<br />
Notification service<br />
SNS = is pub sub service<br />
it publish notification to topic then many application (lambda) subscribe it<br />
</p>
<p>SQS queue = hold message<br />
<br />
EventBridge =<br />
similar to SNS + more</p>
<p>Action - Whenever ES2 terminated</p>
<p>- Whenever Lambda fun get updated</p>
<p>- Whenever conf in dynamodb change</p>
<p></p>
<p>Step Fun =<br />
help to define work flow</p>
<p></p>
<p></p></td>
</tr>
</tbody>
</table>
