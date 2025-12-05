
**🔑 Public Key & Private Key — The Basics**
These are part of a **cryptographic system** called **asymmetric encryption**, where:
- **Public Key**: Can be shared with anyone.
- **Private Key**: Must be kept secret.
They are **mathematically linked**, but you **can't derive** the private key from the public key easily (that’s the magic of cryptography 😄).

**💡 How It Works**
There are **two major uses** of this system:

**1. Encryption / Decryption (for Confidentiality)**
Imagine you want to send a secret message to someone.
- 🔐 **You encrypt the message using their *public key*.**
- 🗝️ **Only they can decrypt it using their *private key*.**
So:

Encrypt with Public Key ➡ Decrypt with Private Key
🧠 Only the person with the correct private key can unlock the message.

**2. Digital Signatures (for Authenticity & Integrity)**
This is to **prove a message came from you** and **wasn’t changed**.
- 🖋️ You sign a message with your **private key**.
- ✅ Anyone can verify it using your **public key**.
So:

Sign with Private Key ➡ Verify with Public Key

**📍 Where Do We Use This?**
1.  **SSL/TLS (HTTPS websites)**
    - **Your browser uses a website's public key to establish a secure connection.**
2.  **SSH (for secure remote login)**
    - **You use your private key to authenticate yourself on a remote server that has your public key.**
3.  **Cryptocurrencies (like Bitcoin, Ethereum)**
    - **Your private key gives access to your funds, and your public key is like your wallet address.**
4.  **Email encryption (like PGP/GPG)**
    - **Send secure emails using the recipient’s public key and decrypt using your private key.**
5.  **JWTs and API Authentication**
    - **Digital signatures ensure data or tokens haven’t been tampered with.**

**🔐 Summary**
| **Action**         | **Uses Which Key?** | **Who Uses It?** |
|--------------------|---------------------|------------------|
| Encrypt a message  | Public key          | Sender           |
| Decrypt a message  | Private key         | Receiver         |
| Sign a message     | Private key         | Sender           |
| Verify a signature | Public key          | Receiver         |

**🔁 Summary of the Flow**
| **Step** | **Action**                            |
|----------|---------------------------------------|
| 1️⃣       | Server has your **public key**        |
| 2️⃣       | SSH client connects                   |
| 3️⃣       | Server sends **encrypted challenge**  |
| 4️⃣       | Client **decrypts using private key** |
| 5️⃣       | Sends response                        |
| 6️⃣       | Server verifies and grants access     |

