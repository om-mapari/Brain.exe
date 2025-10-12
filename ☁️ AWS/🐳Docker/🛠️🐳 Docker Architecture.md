
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>⚙️ <strong>Docker Engine</strong></p>
<p>Docker Engine is responsible for building, running, and managing containers.</p>
<p>It consists of:</p>
<ul>
<li><p>Docker Daemon (dockerd) – Runs in the background and listens for API requests.</p></li>
<li><p>Docker CLI (docker) – Used to interact with the daemon.</p></li>
<li><p>REST API – Allows communication between the Docker CLI and daemon.</p></li>
</ul>
<p></p>
<p></p>
<p>🔌 Default Docker Ports</p>
<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th>Port </th>
<th>Purpose</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>2376 </td>
<td>Secure (TLS/SSL) communication between Docker hosts and clients.</td>
</tr>
<tr class="even">
<td>2375 </td>
<td>Insecure, non-TLS communication.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>🌐 <strong>Remote Docker Engine</strong></p>
<p>Used to execute Docker commands on a remote machine.</p>
<blockquote>
<p>Example: Running an Nginx container on a remote Docker host:</p>
</blockquote>
<p></p>
<p>docker -H=&lt;Remote_IP&gt;:2375 run nginx</p>
<p></p>
<p>Use 2376 for secure communication with TLS encryption.</p>
<p>📂 <strong>Docker’s Layered Architecture:</strong></p>
<ul>
<li><p>Docker uses a layered file system, where each layer is immutable.</p></li>
<li><p>If a build fails at a certain layer, Docker can cache previous layers and restart from the failed layer.</p></li>
</ul>
<p></p>
<p>![image1](../images/acdca01f6f6f4f91b155d1bb0fefdcf6.png)</p>
<p></p>
<p></p>
<p>🛑 <strong>Key Benefits of Layered Architecture:</strong></p>
<p>✅ Improved build efficiency with caching.</p>
<p>✅ Reduces storage requirements.</p>
<p>✅ Enables portability across different environments</p>
<p>✅ If two Dockerfiles have the same set of instructions as start except for the source code, Docker reuses the cache existing layers from the first build, reducing redundancy and speeding up the build process.</p>
<p></p>
<p></p>
<p>🛠️ <strong>Container Layer (Writable Layer):</strong></p>
<ul>
<li><p>When a container runs from an image, Docker adds a thin writable layer on top of the image's layers.</p></li>
<li><p>This writable layer allows modifications like file creation or configuration changes.</p></li>
<li><p>Once the container is stopped, the writable layer is deleted unless explicitly saved.</p></li>
</ul>
<p>+--------------------+</p>
<p>| Writable Layer OR |</p>
<p>| Container Layer |</p>
<p>+--------------------+</p>
<p>|  Layer 3 (RUN)  |</p>
<p>+--------------------+</p>
<p>|  Layer 2 (COPY)  |</p>
<p>+--------------------+</p>
<p>|  Layer 1 (FROM)  |</p>
<p>+--------------------+</p>
<p>|  Base Image (OS) |</p>
<p>+--------------------+</p>
<p></p>
<p></p>
<p><strong>🔄 Copy-on-Write (CoW) Mechanism</strong></p>
<ul>
<li><p>Docker images are immutable, meaning they cannot be modified once created.</p></li>
<li><p>When a container is started from an image, a read-write layer (container layer) is added on top of the existing read-only image layers.</p></li>
<li><p>If a file inside the container needs modification, Docker copies it from the image layer to the writable container layer before making changes.</p></li>
<li><p>This approach ensures that the original image remains unchanged, allowing multiple containers to share the same image efficiently.</p></li>
</ul>
<blockquote>
<p></p>
</blockquote>
<p>![image2](../images/84d335bf2bd244d7bffcd44af9360d3b.png)</p>
<p></p>
<blockquote>
<p></p>
</blockquote>
<p><strong>⚠️ Data Persistence in Containers</strong></p>
<ul>
<li><p>The writable container layer is temporary—any changes made inside the container are lost once the container is stopped or deleted.</p></li>
<li><p>To persist data, use volumes, which store data outside the container's ephemeral storage.</p></li>
</ul>
<p></p>
<p>💾 Creating and Using Docker Volumes</p>
<p>1️⃣ Create a volume:docker volume create data_volume</p>
<p>2️⃣ Mount the volume to a container:</p>
<p>docker run -v data_volume:/app/data my_container</p>
<p>This ensures that data remains intact even if the container is stopped or removed.</p>
<p></p>
<p></p>
<p></p>
<p>![image3](../images/9e01c4ab7f9c4d1a9096dc78ed3eaf9f.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

