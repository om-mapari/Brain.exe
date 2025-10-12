
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Docker Components Explained</p>
<p></p>
<p>🛠️ Dockerfile</p>
<p>  • A text file that contains a set of instructions to build a Docker image.</p>
<p>  • Specifies the base image, environment variables, commands to run, and files to copy.</p>
<p>  • Each instruction creates a new layer in the Docker image.</p>
<p>  • Example instructions: FROM, RUN, COPY, ENV, EXPOSE, CMD, etc.</p>
<p>  • Helps in automation and consistency across different environments.</p>
<p></p>
<p>🖼️ Docker Image</p>
<p>  • A lightweight, standalone, and executable package that includes:</p>
<p>    ○ Code</p>
<p>    ○ Runtime</p>
<p>    ○ Libraries</p>
<p>    ○ Environment variables</p>
<p>    ○ System tools</p>
<p>  • Read-only (immutable) and layered, built from the Dockerfile.</p>
<p>  • Can be inherited from a base image (like python:3.9 or ubuntu:20.04).</p>
<p>  • Stored in a registry, such as:</p>
<p>    ○ Docker Hub (public)</p>
<p>    ○ AWS ECR (Elastic Container Registry)</p>
<p>    ○ Azure Container Registry (ACR)</p>
<p></p>
<p>🐳 Docker Container</p>
<p>  • A running instance of a Docker image.</p>
<p>  • Containers are isolated environments that run applications.</p>
<p>  • Multiple containers can be created from the same image.</p>
<p>  • Containers share the same kernel as the host machine but have their own file system, network, and processes.</p>
<p>  • By default, a container only lives until the process inside is running (e.g., a Node.js app or Python script).</p>
<p></p>
<p>🔥 Container Lifecycle:</p>
<p>  • docker run → Creates and starts a container.</p>
<p>  • docker stop → Stops a running container.</p>
<p>  • docker restart → Restarts a container.</p>
<p>  • docker rm → Removes a container.</p>
<p>  • docker logs → View container logs.</p>
<p></p>
<p></p>
<p>+---------------------------------------------------+</p>
<p>|          Dockerfile           |</p>
<p>|-------------------------------------------------- |</p>
<p>| - Base Image: Node:16-alpine           |</p>
<p>| - ENV variables (NODE_ENV, PORT, DB_HOST)     |</p>
<p>| - Install dependencies              |</p>
<p>| - Copy application code              |</p>
<p>| - Expose port 3000                |</p>
<p>| - CMD to run the app               |</p>
<p>+---------------------------------------------------+</p>
<p>      ↓</p>
<p>      ↓  Docker Build Command</p>
<p>      ↓  `docker build -t myapp .`</p>
<p>+---------------------------------------------------+</p>
<p>|          Docker Image          |</p>
<p>|-------------------------------------------------- |</p>
<p>| - Contains code, runtime, libraries, env vars   |</p>
<p>| - Layered structure                |--&gt; | Push to Docker Hub | ECR |</p>
<p>| - Immutable and reusable             |</p>
<p>| - Stored in Docker Hub or private registry    |</p>
<p>+---------------------------------------------------+</p>
<p>      ↓</p>
<p>      ↓  Docker Run Command</p>
<p>      ↓  `docker run -d -p 3000:3000 myapp`</p>
<p>+---------------------------------------------------+</p>
<p>|        Docker Container          |</p>
<p>|---------------------------------------------------|</p>
<p>| - Running instance of the image          |</p>
<p>| - Isolated environment              |</p>
<p>| - Own file system, network, and processes     |</p>
<p>| - Runs app on port 3000              |</p>
<p>| - Dies when process stops             |</p>
<p>+---------------------------------------------------+</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
