
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🔍 How Docker Containerization Works Under the Hood</p>
<p></p>
<p>1️⃣ Namespaces (Isolation) 🏠</p>
<ul>
<li><p>Ensures each container runs in its own isolated environment.</p></li>
<li><p>Each container gets:</p>
<ul>
<li><p>PID namespace → Isolated process IDs</p></li>
<li><p>NET namespace → Own network stack</p></li>
<li><p>MNT namespace → Own filesystem</p></li>
<li><p>UTS namespace → Separate hostname &amp; domain</p></li>
<li><p>IPC namespace → Shared memory isolation</p></li>
</ul></li>
</ul>
<blockquote>
<p></p>
</blockquote>
<p>2️⃣ Cgroups (Resource Limits) - Control Group 📊</p>
<ul>
<li><p>Controls and limits resource allocation for containers.</p></li>
<li><p>Ensures no single container can consume excessive CPU/memory.</p>
<ul>
<li><p>Examples:</p></li>
</ul></li>
</ul>
<table>
<colgroup>
<col style="width: 52%" />
<col style="width: 47%" />
</colgroup>
<thead>
<tr class="header">
<th>Limit CPU usage to 50%:</th>
<th>docker run --cpus=.5 ubuntu</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Limit memory to 100MB:</td>
<td>docker run --memory=100m ubuntu</td>
</tr>
<tr class="even">
<td>Limit container to 2 CPU cores and 512MB RAM:</td>
<td>docker run --cpus=2 --memory=512m ubuntu</td>
</tr>
</tbody>
</table>
<p></p>
<p>3️⃣ UnionFS (Copy-on-Write Storage) 📂</p>
<ul>
<li><p>Docker uses Union File System (UnionFS) to manage storage layers efficiently.</p></li>
<li><p>When a container starts, it gets a read-only image layer.</p></li>
<li><p>A writable layer is created on top, allowing changes without modifying the base image.</p></li>
</ul>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
