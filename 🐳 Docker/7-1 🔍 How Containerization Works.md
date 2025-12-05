# 🔍 How Docker Containerization Works Under the Hood

## 1️⃣ Namespaces (Isolation) 🏠

Ensures each container runs in its own isolated environment.

Each container gets:
- **PID namespace** → Isolated process IDs
- **NET namespace** → Own network stack
- **MNT namespace** → Own filesystem
- **UTS namespace** → Separate hostname & domain
- **IPC namespace** → Shared memory isolation

## 2️⃣ Cgroups (Resource Limits) - Control Group 📊

Controls and limits resource allocation for containers.
Ensures no single container can consume excessive CPU/memory.

**Examples:**

| Action | Command |
|--------|---------|
| **Limit CPU usage to 50%** | `docker run --cpus=.5 ubuntu` |
| **Limit memory to 100MB** | `docker run --memory=100m ubuntu` |
| **Limit container to 2 CPU cores and 512MB RAM** | `docker run --cpus=2 --memory=512m ubuntu` |

## 3️⃣ UnionFS (Copy-on-Write Storage) 📂

- Docker uses Union File System (UnionFS) to manage storage layers efficiently
- When a container starts, it gets a read-only image layer
- A writable layer is created on top, allowing changes without modifying the base image