
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><table>
<colgroup>
<col style="width: 28%" />
<col style="width: 43%" />
<col style="width: 28%" />
</colgroup>
<thead>
<tr class="header">
<th>Format</th>
<th>Example</th>
<th>Meaning</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Official Image</td>
<td>docker pull ubuntu</td>
<td>Pulls from Docker's official repo</td>
</tr>
<tr class="even">
<td>Username/Image</td>
<td>docker pull ommapari/app</td>
<td>Pulls from a specific Docker Hub user</td>
</tr>
<tr class="odd">
<td>Private Registry</td>
<td>docker pull 123456789012.dkr.ecr.us-east-1.amazonaws.com/my-app</td>
<td>Pulls from a private registry</td>
</tr>
<tr class="even">
<td>With Tag</td>
<td>docker pull nginx:1.23.4</td>
<td>Pulls a specific version</td>
</tr>
<tr class="odd">
<td>With Digest</td>
<td>docker pull nginx@sha256:xyz</td>
<td><p>Pulls a fixed image version<br />
</p>
<p><strong>Why use digests?</strong> Guarantees that the pulled image <strong>never changes</strong>, unlike latest.</p></td>
</tr>
</tbody>
</table>
<p></p>
<p>Note: Always login before pulling</p>
<p></p>
<p></p>
<p>Deploy Private Registry and Pull image</p>
<p></p>
<p>docker run -d --name=my-registry -p 5000:5000 --restart always registry:2</p>
<p></p>
<p>docker pull nginx:latest httpd:latest</p>
<p></p>
<p>docker image tag nginx localhost:5000/nginx:latest</p>
<p></p>
<p>docker images                  </p>
<p>REPOSITORY           TAG    IMAGE ID    CREATED     SIZE</p>
<p>localhost:5000/nginx      latest  53a18edff809  6 weeks ago   192MB</p>
<p>nginx              latest  53a18edff809  6 weeks ago   192MB</p>
<p></p>
<p>docker image tag nginx localhost:5000/nginx:latest</p>
<p></p>
<p>curl -X GET localhost:5000/v2/_catalog</p>
<p>{"repositories":["httpd","nginx"]}</p>
<p></p>
<p>docker pull localhost:5000/nginx</p>
<p></p>
<p></p>
<p>![image1](../images/b62cc9a4dacd4c1686a226816037fe02.png)</p>
<p></p>
<p>![image2](../images/12544345e2fe4e958332f7b0e5a4dd17.png)</p>
<p></p>
<p></p>
<p></p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
