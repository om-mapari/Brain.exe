
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>📝 Writing a Dockerfile:</strong></p>
<p></p>
<p>[INSTRUCTION] [ARGUMENTS]</p>
<p><em># Base Image (Layer 1)</em></p>
<p>FROM ubuntu:20.04  </p>
<p><em># Copy code to /app (Layer 2)</em></p>
<p>COPY . /app     </p>
<p><em># Run a command (Layer 3)</em></p>
<p>RUN apt-get update</p>
<p></p>
<p></p>
<p><strong>🔨 Building the Docker Image</strong>📦 <strong>from Dockerfile:</strong></p>
<p></p>
<p>docker build -t [tagName] .</p>
<p></p>
<table>
<colgroup>
<col style="width: 22%" />
<col style="width: 77%" />
</colgroup>
<thead>
<tr class="header">
<th>-t [tagName]:</th>
<th>Assigns a name to the image.</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>. (dot):</td>
<td>Specifies the current directory as the build context, which contains the Dockerfile.</td>
</tr>
</tbody>
</table>
<p></p>
<p></p>
<p></p>
<p><strong>🎸 Basic Instructions:</strong></p>
<p></p>
<ol type="1">
<li><p>`<strong>FROM</strong> python:3.9`</p></li>
</ol>
<p></p>
<ul>
<li><p>Specifies the base image.</p></li>
<li><p>Every Dockerfile starts with FROM. It defines the starting point of the image.</p></li>
</ul>
<p></p>
<p></p>
<ol type="1">
<li><p><strong>RUN</strong> apt-get update &amp;&amp; apt-get install -y curl</p></li>
</ol>
<p></p>
<ul>
<li><p>Executes commands during the image build process (like installing dependencies).</p></li>
</ul>
<p></p>
<p></p>
<ol type="1">
<li><p><strong>COPY</strong> . /app</p></li>
</ol>
<p></p>
<ul>
<li><p>Copies files from the host machine to the container.</p></li>
</ul>
<p></p>
<p></p>
<ol type="1">
<li><p><strong>ADD</strong> myfile.tar.gz /app/</p></li>
</ol>
<p></p>
<ul>
<li><p>Similar to COPY, but supports remote URLs and compressed files.</p></li>
</ul>
<p></p>
<p></p>
<ol type="1">
<li><p>WORKDIR /app</p></li>
</ol>
<p></p>
<ul>
<li><p>Sets the working directory inside the container.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p>EXPOSE 8080</p></li>
</ol>
<p></p>
<ul>
<li><p>Informs Docker about the port the container listens on.</p></li>
<li><p>The EXPOSE command is only informational. It doesn't actually make the port accessible from outside the container.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>ENV</strong> APP_ENV=production</p></li>
</ol>
<p></p>
<ul>
<li><p>Sets environment variables inside the container.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>ENTRYPOINT</strong> ["python", "app.py"]</p></li>
</ol>
<p></p>
<ul>
<li><p>Defines the main executable or command when the container runs.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>CMD</strong> ["--port=8080"]</p></li>
</ol>
<p></p>
<ul>
<li><p>Provides default arguments for ENTRYPOINT.</p></li>
</ul>
<p></p>
<p>🚀 Advanced Instructions:</p>
<p></p>
<ol type="1">
<li><p><strong>ARG VERSION</strong>=1.0</p></li>
</ol>
<p></p>
<ul>
<li><p>Defines build-time variables.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>VOLUME</strong> /data</p></li>
</ol>
<p></p>
<ul>
<li><p>Creates a mount point for persistent storage.</p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>USER</strong> appuser</p></li>
</ol>
<p></p>
<ul>
<li><p>Switches to a non-root user inside the container.</p></li>
</ul>
<blockquote>
<p></p>
</blockquote>
<ol type="1">
<li><p><strong>HEALTHCHECK</strong> --interval=30s CMD curl -f <a href="http://localhost/"><strong>http:<em>//localhost/</em></strong></a> <em>|| exit 1</em></p></li>
</ol>
<p></p>
<ul>
<li><p>Defines a health check command to monitor the container's status<em>.</em></p></li>
</ul>
<p></p>
<ol type="1">
<li><p><strong>LABEL</strong> version="1.0" author="Om"</p></li>
</ol>
<p></p>
<ul>
<li><p>Adds metadata information (like version or author).</p></li>
</ul>
<p></p>
<p></p>
<p>✅ Bonus Tip: Best Practice Structure (stage building)</p>
<p></p>
<p></p>
<p><em># Base image (Alpine for lightweight build)</em></p>
<p>FROM node:16-alpine as builder</p>
<p></p>
<p><em># Set working directory</em></p>
<p>WORKDIR /app</p>
<p></p>
<p><em># Install dependencies separately for better caching</em></p>
<p>COPY package*.json ./</p>
<p>RUN npm install --production</p>
<p></p>
<p><em># Copy the application code</em></p>
<p>COPY . .</p>
<p></p>
<p><em># Run build step (if needed)</em></p>
<p>RUN npm run build</p>
<p></p>
<p><em># Multi-stage build to keep final image lightweight</em></p>
<p>FROM node:16-alpine</p>
<p></p>
<p><em># Set working directory</em></p>
<p>WORKDIR /app</p>
<p></p>
<p><em># Copy only the built files and node_modules from the builder stage</em></p>
<p>COPY --from=builder /app/node_modules ./node_modules</p>
<p>COPY --from=builder /app/dist ./dist</p>
<p></p>
<p><em># Set environment variables</em></p>
<p>ENV NODE_ENV=production \</p>
<p>  PORT=3000 \</p>
<p>  DB_HOST=localhost \</p>
<p>  DB_USER=admin</p>
<p></p>
<p><em># Expose port</em></p>
<p>EXPOSE 3000</p>
<p></p>
<p><em># Set non-root user for security</em></p>
<p>USER node</p>
<p></p>
<p><em># Run the application</em></p>
<p>CMD ["node", "dist/server.js"]</p>
<p></p>
<p></p>
<p>📚 Pro Tip:</p>
<p>  • Always use minimal base images (like alpine) to keep the image lightweight.</p>
<p>  • Combine multiple RUN commands to reduce layers and optimize caching.</p>
<p>• Setting non-root user (USER node) for better security.</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
