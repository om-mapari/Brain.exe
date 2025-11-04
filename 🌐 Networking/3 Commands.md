

---

> “Let’s see what happens when I open `https://www.google.com` in my browser. Behind the scenes, multiple networking layers work together.”

---

### 2️⃣ **Step 2: DNS Lookup — (Application Layer)**

Command:

```bash
nslookup om-mapari.com
```

![[../attachments/3 Tracing a Web Request.. From My Laptop to the Server-1.webp]]

---

### 3️⃣ **Step 3: Connectivity Check — (Network Layer / ICMP)**

Command:

```bash
ping www.google.com
```

![[../attachments/2 Common command we USE-1.webp|825]]

---

### 4️⃣ **Step 4: Route Discovery — (Network Layer / Routing)**

Command:

```bash
tracert www.google.com
```


- Shows all the **routers/hops** between you and Google.
    
- Each hop = a device (router) your packet crosses.
    
- Sometimes you’ll see private IPs (like `192.168.x.x`) — that’s your internal network.

💡 _Relate to OSI Layers:_ Routers operate at **Layer 3 (Network)** — they forward packets based on IP.



![[../attachments/3 Tracing a Web Request.. From My Laptop to the Server.webp]]

```
C:\Users\mapar>curl -I https://om-mapari.com/
```
![[../attachments/3 Tracing a Web Request.. From My Laptop to the Server-2.webp]]
---
![[../attachments/3 Tracing a Web Request.. From My Laptop to the Server-3.webp]]