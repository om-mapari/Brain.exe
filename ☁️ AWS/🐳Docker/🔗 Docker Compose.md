
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🌟 What is Docker Compose?</p>
<ul>
<li><p>A tool for defining and managing multi-container Docker applications.</p></li>
<li><p>Allows starting multiple containers in one go using a single YAML file</p></li>
</ul>
<blockquote>
<p>(docker-compose.yml).</p>
<p></p>
</blockquote>
<p>why?</p>
<p></p>
<p>![image1](../images/23b546c7e287479abec53dcc6b3031d9.png)</p>
<p></p>
<p></p>
<p>🛠️ Basic Structure of docker-compose.yml:</p>
<p></p>
<p>version: '3.8' <em># Docker Compose version</em></p>
<p>services: </p>
<p> app_service: <em># Name of the service (container)</em></p>
<p>  image: my_app_image <em># or ./vote # location to Dockerfile</em></p>
<p>  ports:</p>
<p>   - "8080:80" <em># Port mapping (host:container)</em></p>
<p>  links:</p>
<p>   - db_service <em># Deprecated: Was used to Linking to another service</em></p>
<p>  networks:</p>
<p>   - app_network <em># Custom network</em></p>
<p>  depends_on:</p>
<p>   - db_service <em># Ensure the database starts first</em></p>
<p>  environment:</p>
<p>   - APP_ENV=production</p>
<p> db_service:</p>
<p>  image: mysql:5.7</p>
<p>  environment:</p>
<p>   MYSQL_ROOT_PASSWORD: example</p>
<p>  volumes:</p>
<p>   - db_data:/var/lib/mysql</p>
<p>networks:</p>
<p> app_network:</p>
<p>volumes:</p>
<p> db_data:</p>
<p></p>
<p></p>
<p>🛠️ Key Docker Compose Components:</p>
<table>
<colgroup>
<col style="width: 31%" />
<col style="width: 68%" />
</colgroup>
<thead>
<tr class="header">
<th>Services:</th>
<th>Defines individual containers (like app and database).</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Ports Mapping (ports):</td>
<td>Maps ports between host and container.</td>
</tr>
<tr class="even">
<td><p>Links (links)</p>
<p>(Deprecated in v3+):</p></td>
<td>Adds entries to the /etc/hosts file to allow container communication.</td>
</tr>
<tr class="odd">
<td>Depends On (depends_on):</td>
<td>Ensures one service starts after another.</td>
</tr>
<tr class="even">
<td>Networks (networks):</td>
<td>Creates isolated networks for secure communication.</td>
</tr>
<tr class="odd">
<td>Volumes (volumes):</td>
<td>Persistent data storage between container restarts.</td>
</tr>
<tr class="even">
<td>Build Context (build):</td>
<td><p>When a Dockerfile is available, specify the build directory.<br />
<br />
</p>
<p>build: ./app_directory </p></td>
</tr>
</tbody>
</table>
<p></p>
<p>🚀 Commands to Run Docker Compose:</p>
<table>
<colgroup>
<col style="width: 40%" />
<col style="width: 59%" />
</colgroup>
<thead>
<tr class="header">
<th>docker-compose up -d</th>
<th>Start containers in the background:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>docker-compose down</td>
<td>Stop running containers:</td>
</tr>
<tr class="even">
<td>docker-compose logs</td>
<td>View logs:</td>
</tr>
<tr class="odd">
<td>docker-compose up --scale app_service=3</td>
<td>Scale services:</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p>link Add entry to the host file of voting-appp</p>
<p></p>
<p>--link redis:redis</p>
<p>containerName:NameOfHostAppLookingFor(in code i guess)</p>
<p></p>
<p>![image2](../images/43e1f7f7742d4c2b994bdd6658bcf331.png)</p>
<p></p>
<p>![image3](../images/afd69e28438440d2bb06c002c3c8b566.png)</p>
<blockquote>
<p></p>
</blockquote>
<p>![image4](../images/de0fafbbf1db4167a60a5800018fda0c.png)</p>
<p></p>
<p></p>
<p></p>
<p>Network</p>
<p></p>
<p>![image5](../images/ee59119129a0420db4994243ebfdd9b2.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
