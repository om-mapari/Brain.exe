
<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>🐳 Docker Startup Commands - CMD vs ENTRYPOINT</p>
<p></p>
<p>CMD (Command Directive):</p>
<ul>
<li><p>Provides default command to run when the container starts.</p></li>
<li><p>Can be overwritten at runtime.</p></li>
</ul>
<p></p>
<p>✅ Syntax: CMD ["command", "param1"] or CMD command param1</p>
<blockquote>
<p></p>
<p></p>
</blockquote>
<p></p>
<p>🚀 ENTRYPOINT (Entrypoint Directive):</p>
<ul>
<li><p>Sets the executable, making the container behave like a standalone application.</p></li>
<li><p>Arguments passed during docker run are appended to the entrypoint.</p></li>
</ul>
<blockquote>
<p></p>
</blockquote>
<p>✅ Syntax: ENTRYPOINT ["command"]</p>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 71%" />
</colgroup>
<thead>
<tr class="header">
<th><p>FROM ubuntu </p>
<p>CMD ["sleep", "5"]</p></th>
<th><p>once run will terminate after 5 sec<br />
</p>
<p>Overriding CMD:</p>
<p>docker run ubuntu-sleeper sleep 10</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p></p>
<p></p>
<p></p>
<p></p>
<table>
<colgroup>
<col style="width: 28%" />
<col style="width: 71%" />
</colgroup>
<thead>
<tr class="header">
<th><p>FROM ubuntu </p>
<p>ENTRYPOINT ["sleep"]</p></th>
<th><p>Running the container with an argument:</p>
<p></p>
<p>docker run ubuntu-sleeper 10</p>
<p></p>
<p>10 gets appened to entrypoint command</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
<p></p>
<p></p>
<p>![image1](../images/53347c2cd3cd4d6d95cbf7bc1fbe33df.png)</p>
<p></p>
<p>Using both Command and Entrypoint instruction</p>
<p>![image2](../images/a8ff85287d9040ce89b568adbb0ab726.png)</p>
<p></p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>
