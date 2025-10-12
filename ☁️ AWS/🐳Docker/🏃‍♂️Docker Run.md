
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p></p>
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🐳 Mastering the docker run Command<br />
</p>
<p></p>
<p>docker run [OPTIONS] IMAGE_NAME[:TAG] [COMMAND] [ARG...]</p>
<p></p>
<p>If the tag version is not specified, Docker defaults to latest.</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 45%" />
<col style="width: 54%" />
</colgroup>
<thead>
<tr class="header">
<th>⚙️ Common Options:</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>--name </td>
<td>Assigns a custom name to the container.</td>
</tr>
<tr class="even">
<td>-e or --env</td>
<td>Sets environment variables inside the container.</td>
</tr>
<tr class="odd">
<td>-d or --detach </td>
<td>Runs the container in detached mode (background).</td>
</tr>
<tr class="even">
<td>-p or --publish</td>
<td>Maps container port to host port (host_port:container_port).</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 36%" />
<col style="width: 63%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🛠️ Executing Commands in a Container:</p>
<p>docker run ubuntu sleep 5</p></th>
<th><p>Starts the container →</p>
<p>Runs sleep for 5 seconds →</p>
<p>Stops the container.<br />
<br />
</p>
<p>Verify the execution:</p>
<p>docker ps -a</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>📂 Accessing Files in a Running Container:</p>
<p>docker exec [containerID] cat /etc/hosts</p></td>
<td>Prints the content of the hosts file.</td>
</tr>
<tr class="even">
<td><p>🔗 Attach, Detach, and Reattach:</p>
<p>docker run -d ubuntu</p></td>
<td>![image1](../images/d594a54e6a684551a92b333654f4f4e7.png)</td>
</tr>
<tr class="odd">
<td><p>🖥️ Interactive Mode:<br />
<br />
docker run -it centos bash</p>
<p></p></td>
<td><p>-i: Interactive input.</p>
<p>-t: Attach to the terminal.</p>
<p>Opens the Bash shell inside the container.</p></td>
</tr>
<tr class="even">
<td><p>🌐 Port Mapping:</p>
<p>docker run -p 80:5000 kodekloud/webapp</p></td>
<td><p>80: Host port.</p>
<p>5000: Container port.</p></td>
</tr>
<tr class="odd">
<td><p>📂 Volume Mapping (Persistent Data):</p>
<p>docker run -v /opt/datadir:/var/lib/mysql mysql</p></td>
<td>Maps the external folder /opt/datadir to the MySQL container's data directory.</td>
</tr>
<tr class="even">
<td>🔎 Inspect Container Details:<br />
<br />
docker inspect [containerName]</td>
<td><p>![image2](../images/47b62ae020e747a1aeae01d80ec19b77.png)</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>📝 Viewing Container Logs:<br />
</p>
<p>docker logs [containerName]</p></td>
<td><p>![image3](../images/6d8402bc931e45c5917c5d9fee951772.png)</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>🌈 Setting Environment Variables:<br />
</p>
<p>docker run -e APP_COLOR=blue simple-webapp</p></td>
<td><p>Verify the environment variable:</p>
<p>docker inspect [containerName]</p></td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p> </p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
