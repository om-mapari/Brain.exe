---
title: jq JSON Processor
description: Lightweight command-line JSON processor for querying, filtering, and manipulating JSON data
tags:
    - linux
    - json
    - commands
    - devops
    - docker
created: 2025-12-31
updated: 2025-12-31
---
---

# jq JSON Processor

## What is jq?

jq is a **lightweight and powerful command-line JSON processor**. It allows you to **query, filter, format, and manipulate JSON data** directly from the terminal.

## Why use jq?

- Pretty-prints JSON data.
- Extracts specific fields from JSON.
- Modifies JSON values.
- Works well with APIs, logs, and Docker commands.

## Installing jq

### Linux (Ubuntu/Debian)

```bash
sudo apt install jq -y
```

### MacOS (Homebrew)

```bash
brew install jq
```

### Windows (Chocolatey)

```bash
choco install jq
```

## Example Usage

### 1️⃣ Pretty-print JSON

```bash
echo '{"name":"Om","role":"DevOps"}' | jq
```

**Output:**

```json
{  
  "name": "Om",  
  "role": "DevOps"  
}
```

### 2️⃣ Extract a specific field

```bash
docker image inspect kodekloud/simple-webapp-mysql | jq '.[0].Config.ExposedPorts'
```

**Output:**

```json
{  
  "8080/tcp": {}  
}
```

### 3️⃣ Get a specific key-value

```bash
docker image inspect kodekloud/simple-webapp-mysql | jq '.[0].Config.Env'
```

This extracts all environment variables.

## Why is jq better than grep?

- jq understands JSON structure, while grep just searches for text.
- jq provides cleaner and more accurate output.
- jq avoids mistakes when dealing with multi-line or nested JSON.

> [!tip]
> 🚀 **Pro Tip:** If you're working with JSON frequently (AWS CLI, Kubernetes, Docker, APIs), **learning jq is a game-changer**!

## Related Topics

- [[1 IP Commands]]
- [[2 Volume Mounting]]
- [[3 sudo Command]]

---
