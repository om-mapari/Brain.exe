---

# 🌐 DNS (Domain Name System) - The Internet's Phone Book

**📌 What is DNS?**
- ✔️ **Domain Name System** - translates human-readable domain names into IP addresses
- ✔️ **Distributed database** that maps domain names to IP addresses
- ✔️ **Essential service** that makes the internet user-friendly

---

## 🔄 How DNS Works

### 1️⃣ **The Problem DNS Solves**
- 💡 **Humans remember names** → `google.com`, `github.com`
- 💡 **Computers use numbers** → `142.250.191.14`, `140.82.112.4`
- 💡 **DNS bridges this gap** by translating names to numbers

### 2️⃣ **DNS Resolution Process**

```
User types: google.com
     ↓
1️⃣ Browser checks local cache
     ↓
2️⃣ Queries DNS Resolver (ISP)
     ↓
3️⃣ Root DNS Server (.com, .org, .net)
     ↓
4️⃣ TLD Server (Top Level Domain)
     ↓
5️⃣ Authoritative Name Server
     ↓
6️⃣ Returns IP: 142.250.191.14
```

---

## 🏗️ DNS Hierarchy Structure

### **📍 Root Domain Servers**
- ✔️ **Top level** of DNS hierarchy
- ✔️ **13 root server clusters** worldwide
- ✔️ **Know about TLD servers** (.com, .org, .net, .in)

### **📍 TLD (Top Level Domain) Servers**
- ✔️ **Manage specific extensions** (.com, .org, .net, .in)
- ✔️ **Know authoritative servers** for each domain
- ✔️ **Examples**: `.com`, `.org`, `.net`, `.in`, `.uk`

### **📍 Authoritative Name Servers**
- ✔️ **Final authority** for a specific domain
- ✔️ **Contains actual DNS records** (A, AAAA, CNAME, MX)
- ✔️ **Managed by domain owner** or hosting provider

---

## 📋 Common DNS Record Types

| **Record Type** | **Purpose** | **Example** |
|-----------------|-------------|-------------|
| **A** | Maps domain to IPv4 address | `google.com → 142.250.191.14` |
| **AAAA** | Maps domain to IPv6 address | `google.com → 2404:6800:4007:81b::200e` |
| **CNAME** | Alias for another domain | `www.example.com → example.com` |
| **MX** | Mail server records | `example.com → mail.example.com` |
| **NS** | Name server records | `example.com → ns1.example.com` |
| **TXT** | Text records (verification) | `example.com → "v=spf1 include:_spf.google.com ~all"` |

---

## 🚀 DNS in Action - Real Example

**🌐 When you visit `github.com`:**

1️⃣ **Browser Cache Check**
   - Checks if `github.com` IP is already cached
   - If found → uses cached IP (faster)

2️⃣ **DNS Resolver Query** (Your ISP)
   - Browser asks ISP's DNS resolver
   - Resolver checks its cache first

3️⃣ **Root Server Query**
   - Resolver asks root server: "Who handles .com?"
   - Root server responds: "Ask .com TLD server"

4️⃣ **TLD Server Query**
   - Resolver asks .com server: "Who handles github.com?"
   - TLD server responds: "Ask ns-1707.awsdns-21.co.uk"

5️⃣ **Authoritative Server Query**
   - Resolver asks GitHub's name server
   - Returns: `github.com → 140.82.112.4`

6️⃣ **Response to Browser**
   - Browser receives IP address
   - Connects to `140.82.112.4`

---

## ⚡ DNS Caching & Performance

### **📌 Caching Levels**
- 🔄 **Browser Cache** → 1-30 minutes
- 🔄 **OS Cache** → System-level caching
- 🔄 **Router Cache** → Local network caching
- 🔄 **ISP Cache** → Provider-level caching

### **💡 TTL (Time To Live)**
- ✔️ **Controls cache duration** for DNS records
- ✔️ **Lower TTL** = More frequent updates, slower
- ✔️ **Higher TTL** = Less frequent updates, faster

---

## ☁️ AWS Route 53 - Managed DNS Service

### **📌 What is Route 53?**
- ✔️ **AWS managed DNS service**
- ✔️ **Highly available** and scalable
- ✔️ **Global network** of DNS servers

### **🛠️ Route 53 Features**
- 🌐 **Domain registration** and management
- 🎯 **Health checks** and failover
- 🔄 **Traffic routing policies** (weighted, latency-based)
- 📊 **DNS query logging** and monitoring

### **💰 Route 53 Pricing**
- 💵 **$0.50 per hosted zone** per month
- 💵 **$0.40 per million queries** (first 1 billion)
- 💵 **Domain registration** varies by TLD

---

## 🔧 DNS Troubleshooting Commands

### **🐧 Linux/Mac Commands**
```bash
# Basic DNS lookup
nslookup google.com

# Detailed DNS information
dig google.com

# Trace DNS resolution path
dig +trace google.com

# Check specific record type
dig google.com MX
dig google.com AAAA
```

### **🪟 Windows Commands**
```cmd
# Basic DNS lookup
nslookup google.com

# Flush DNS cache
ipconfig /flushdns

# Display DNS cache
ipconfig /displaydns
```

---

## 🔒 DNS Security Considerations

### **⚠️ Common DNS Attacks**
- 🚨 **DNS Spoofing** → Fake DNS responses
- 🚨 **DNS Hijacking** → Redirecting DNS queries
- 🚨 **DDoS on DNS** → Overwhelming DNS servers

### **🛡️ DNS Security Solutions**
- ✔️ **DNSSEC** → Digital signatures for DNS records
- ✔️ **DNS over HTTPS (DoH)** → Encrypted DNS queries
- ✔️ **DNS over TLS (DoT)** → TLS encryption for DNS
- ✔️ **Use trusted DNS providers** → Cloudflare (1.1.1.1), Google (8.8.8.8)

---

## 📚 Key Takeaways

- 🎯 **DNS translates** domain names to IP addresses
- 🎯 **Hierarchical system** with root, TLD, and authoritative servers
- 🎯 **Caching improves performance** at multiple levels
- 🎯 **Route 53 provides** managed DNS with advanced features
- 🎯 **Security is important** - use DNSSEC and encrypted DNS

---