
What is a Port?
  • A port is a virtual endpoint used for communication between devices over a network.
  • Ports help in identifying specific services running on a system.
  • Each port is associated with a protocol (TCP/UDP).

Categories of Ports

<table>
<colgroup>
<col style="width: 43%" />
<col style="width: 56%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1️⃣ Well-Known Ports</p>
<p>(0 - 1023) →</p></th>
<th><p>Used by standard services</p>
<p>(e.g., HTTP, SSH, DNS).</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2️⃣ Registered Ports</p>
<p>(1024 - 49151) →</p></td>
<td><p>Used by applications</p>
<p>(e.g., MySQL, PostgreSQL).</p></td>
</tr>
<tr class="even">
<td><p>3️⃣ Dynamic / Ephemeral Ports</p>
<p>(49152 - 65535) →</p></td>
<td>Temporary ports for client connections.</td>
</tr>
</tbody>
</table>

Important Ports to Remember 🔥

| Port         | Service                       | Protocol | Use Case                            |
| ------------ | ----------------------------- | -------- | ----------------------------------- |
| 🔒 22        | SSH (Secure Shell)            | TCP      | Secure remote access to servers     |
| 🌍 80/443    | HTTP/HTTPS                    | TCP      | Web browsing & API requests         |
| 📦 20/21     | FTP (File Transfer Protocol)  | TCP      | Transferring files between servers  |
| 🐳 2375/2376 | Docker API                    | TCP      | Managing Docker containers remotely |
| 🖥️ 3389     | RDP (Remote Desktop Protocol) | TCP      | Accessing Windows servers remotely  |
| 🗄️ MongoDB  | 27017                         | TCP      | Conn to MongoDB on a remote server  |
| 🐍 3306      | MySQL                         | TCP      | Connecting to MySQL databases       |
| 🦾 5432      | PostgreSQL                    | TCP      | Connecting to PostgreSQL databases  |
| 📊 9090      | Prometheus                    | TCP      | Monitoring and metrics collection   |
| 📈 3000      | Grafana                       | TCP      | Visualizing monitoring data         |
| 🕵️ 53       | DNS (Domain Name System)      | UDP/TCP  | Resolving domain names to IPs       |
| ⏰ 123        | NTP (Network Time Protocol)   | UDP      | Synchronizing system time           |

Note: If you're running MongoDB on a remote server, ensure port 27017 is open in your firewall or security groups.

How Ports Work?
1️⃣ A client sends a request to a server’s IP address & port.
2️⃣ The server listens on that port for incoming connections.
3️⃣ The connection is established, and data transfer begins.

TCP vs. UDP Ports
✅ TCP (Transmission Control Protocol) – Reliable, connection-oriented
(e.g., HTTPS, SSH).
✅ UDP (User Datagram Protocol) – Fast, connectionless
(e.g., DNS, Streaming).

AWS Security Groups & Ports
  • Security Groups allow or deny inbound & outbound traffic based on port numbers.
  • Example:
    ○ Allow SSH (Port 22) → Access Linux EC2 instances.
    ○ Allow HTTP (Port 80) → Host a website on EC2.

📌 Summary
  • Ports identify services on a system (e.g., 80 → HTTP, 443 → HTTPS).
  • Some ports are well-known, while others are dynamic.
  • TCP is reliable, while UDP is faster but less reliable.
  • AWS Security Groups control access using ports.
Let me know if you need a cheat sheet or a diagram! 🚀🔥

