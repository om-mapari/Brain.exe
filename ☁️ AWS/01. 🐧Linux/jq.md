
**What is jq?**
jq is a **lightweight and powerful command-line JSON processor**. It allows you to **query, filter, format, and manipulate JSON data** directly from the terminal.
**Why use jq?**
- Pretty-prints JSON data.
- Extracts specific fields from JSON.
- Modifies JSON values.
- Works well with APIs, logs, and Docker commands.

**Installing jq**
🔹 **Linux (Ubuntu/Debian)**

sh
CopyEdit
sudo apt install jq -y
🔹 **MacOS (Homebrew)**

sh
CopyEdit
brew install jq
🔹 **Windows (Chocolatey)**

sh
CopyEdit
choco install jq

**Example Usage**
**1️⃣ Pretty-print JSON**

sh
CopyEdit
echo '{"name":"Om","role":"DevOps"}' \| jq
**Output:**

json
CopyEdit
{  
"name": "Om",  
"role": "DevOps"  
}
**2️⃣ Extract a specific field**

sh
CopyEdit
docker image inspect kodekloud/simple-webapp-mysql \| jq '.\[0\].Config.ExposedPorts'
**Output:**

json
CopyEdit
{  
"8080/tcp": {}  
}
**3️⃣ Get a specific key-value**

sh
CopyEdit
docker image inspect kodekloud/simple-webapp-mysql \| jq '.\[0\].Config.Env'
This extracts all environment variables.

**Why is jq better than grep?**
- jq understands JSON structure, while grep just searches for text.
- jq provides cleaner and more accurate output.
- jq avoids mistakes when dealing with multi-line or nested JSON.
🚀 **Pro Tip:** If you're working with JSON frequently (AWS CLI, Kubernetes, Docker, APIs), **learning jq is a game-changer**!
Let me know if you want more examples! 😃
