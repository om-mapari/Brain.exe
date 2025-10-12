
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>4️⃣ Networking (Container Communication) 🌐</p>
<ul>
<li><p>Docker provides multiple networking options:</p>
<ul>
<li><p>Bridge (default network) → Containers on the same host can talk to each other.</p></li>
<li><p>Host → Uses the host network directly (no isolation).</p></li>
<li><p>Overlay → Enables communication across multiple hosts.</p></li>
<li><p>None → No network access.</p></li>
</ul></li>
</ul>
<p></p>
<p>Example: Running a container with port mapping for Bridge Network</p>
<p>docker run -p 8080:80 nginx</p>
<p></p>
<p>Maps port 80 of the container to port 8080 of the host.</p>
<p></p>
<p></p>
<p>Important Docker Networking commands:</p>
<p></p>
<p>🔍 Viewing Networks</p>
<table>
<colgroup>
<col style="width: 47%" />
<col style="width: 52%" />
</colgroup>
<thead>
<tr class="header">
<th>docker network ls</th>
<th>→ List all available Docker networks.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker network inspect &lt;network_id_or_name&gt;</td>
<td>→ Get detailed information about a specific network.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>🌐 Creating &amp; Removing Networks</p>
<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th>docker network create &lt;network_id&gt;</th>
<th>→ Create a new custom network.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker network rm &lt;network_name&gt;</td>
<td>→ Remove a specific network.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>🔗 Connecting &amp; Disconnecting Containers</p>
<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th>docker network connect &lt;network_name&gt; &lt;container_name&gt;</th>
<th>→ Connect a running container to a network.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker network disconnect &lt;network_name&gt; &lt;container_name&gt;</td>
<td>→ Disconnect a container from a network.</td>
</tr>
</tbody>
</table>
<p></p>
<p>🚀 Running Containers with Network Options</p>
<table>
<colgroup>
<col style="width: 46%" />
<col style="width: 53%" />
</colgroup>
<thead>
<tr class="header">
<th>docker run --network &lt;network_name&gt; &lt;image&gt;</th>
<th>→ Start a container in a specific network.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker run --network host &lt;image&gt;</td>
<td>→ Use the host network (no isolation).</td>
</tr>
<tr class="even">
<td>docker run --network none &lt;image&gt;</td>
<td>→ Start a container with no network access.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>🔄 Port Mapping &amp; Communication</p>
<table>
<colgroup>
<col style="width: 52%" />
<col style="width: 47%" />
</colgroup>
<thead>
<tr class="header">
<th>docker run -p &lt;host_port&gt;:&lt;container_port&gt; &lt;image&gt;</th>
<th>→ Map container ports to host ports (default bridge network).</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker exec -it &lt;container_id&gt; ping &lt;another_container&gt;</td>
<td>→ Check communication between containers in the same network.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>bridge is default</p>
<p>![image1](../../images/4318b2e6515f45b1862bb1adf12e8593.png)</p>
<p></p>
<p>![image2](../../images/ff2fbe80a6964ac581c7ca8ab26241dd.png)</p>
<p></p>
<p>![image3](../../images/da63c442d5c84877ab623426708879c9.png)</p>
<p></p>
<p>docker has build in dns server that help container to resolve each other with the name of the container</p>
<p></p>
<p></p>
<p></p>
<p></p>
<p>![image4](../../images/0740c419d6214e608945c8a865e2c3de.png)</p>
<p></p>
<p></p>
<p></p>
<p><em># create network</em></p>
<p>docker network create --driver=bridge --gateway=182.18.0.1 --subnet=182.18.0.0/24 wp-mysql-network </p>
<p></p>
<p><em># create mysql db in network</em></p>
<p>docker run -d --name=mysql-db -e MYSQL_ROOT_PASSWORD=db_pass123 --network=wp-mysql-network mysql:5.6</p>
<p></p>
<p><em># create application in network with link to mysql-db</em></p>
<p>docker run -d --name=webapp -p 38080:8080 -e DB_Host=mysql-db -e DB_Password=db_pass123 --network=wp-mysql-network --link mysql-db:mysql-db kodekloud/simple-webapp-mysql</p>
<p></p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
