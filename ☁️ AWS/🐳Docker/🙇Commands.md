
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🎯 Basic Commands:</p>
<table>
<colgroup>
<col style="width: 54%" />
<col style="width: 45%" />
</colgroup>
<thead>
<tr class="header">
<th>Command</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker build -t [tagName] .</td>
<td>Building the Docker Image📦 from Dockerfile</td>
</tr>
<tr class="even">
<td>docker run [ImageName] </td>
<td>Pulls the image (if not present) and runs the container.</td>
</tr>
<tr class="odd">
<td>docker ps </td>
<td>Lists all running containers (process status).</td>
</tr>
<tr class="even">
<td>docker stop [containerID/containerName]</td>
<td>Stops a running container.</td>
</tr>
<tr class="odd">
<td>docker ps -a  </td>
<td>Lists all containers, including stopped ones.</td>
</tr>
<tr class="even">
<td>docker rm [containerID/containerName] </td>
<td>Removes a container permanently.</td>
</tr>
<tr class="odd">
<td>docker images </td>
<td>Lists all downloaded images with size and Image ID.</td>
</tr>
<tr class="even">
<td>docker image inspect kodekloud/simple-webapp-mysql</td>
<td>to know about</td>
</tr>
<tr class="odd">
<td>docker rmi [imageName/imageID] </td>
<td>Removes an image. (Note: Remove dependent containers first.)</td>
</tr>
<tr class="even">
<td>docker pull [image:version]</td>
<td>Pulls the specified image from Docker Hub.</td>
</tr>
</tbody>
</table>
<p></p>
<p>⚡ Advanced Commands:</p>
<p>Command Description</p>
<table>
<colgroup>
<col style="width: 40%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr class="header">
<th>docker stop $(docker ps -a -q) </th>
<th>Stops all containers.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker rm $(docker ps -a -q)  </td>
<td>Removes all containers.</td>
</tr>
<tr class="even">
<td>docker stop sd pr ms  </td>
<td>Stops multiple containers (e.g., sd, pr, and ms).</td>
</tr>
</tbody>
</table>
<p></p>
<p>🛠️ Accessing the Container Terminal:</p>
<p>Command Description</p>
<table>
<colgroup>
<col style="width: 44%" />
<col style="width: 55%" />
</colgroup>
<thead>
<tr class="header">
<th>docker run -it centos bash </th>
<th>Launches a CentOS container and opens the Bash shell (-it stands for interactive mode).</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>cat /etc/*release* </td>
<td>Shows the OS version inside the container.</td>
</tr>
</tbody>
</table>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

docker rmi \$(docker images) 
