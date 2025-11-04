

![[../attachments/4 DNS Server.webp]] 


### 📘 **DNS Summary for om-mapari.com**

- **Domain:** `om-mapari.com`
    
- **Registrar:** Cloudflare
    
- **Authoritative Name Servers:**
    
    - `norm.ns.cloudflare.com`
        
    - `ollie.ns.cloudflare.com`

---

### ⚙️ **How DNS Lookup Works**

1️⃣ Browser checks local **cache** or **hosts file**.  
2️⃣ If not found → asks **Recursive DNS (ISP)**.  
3️⃣ Recursive DNS → queries **Root DNS** (knows `.com`).  
4️⃣ **TLD (.com)** server → points to **Cloudflare’s NS**.  
5️⃣ **Cloudflare (Authoritative NS)** → returns actual **IP address** of `om-mapari.com`.  
6️⃣ Browser connects to that IP → website loads ✅