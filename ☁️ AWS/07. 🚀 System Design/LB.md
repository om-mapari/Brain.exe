
explain all 3 algos ? Round Robin, Least Connections, IP Hash

⚖️ ASG

ChatGPT said:
You got it, Om! Let's break down the three main load balancing algorithms you'll come across in Kubernetes/EKS Ingress Controllers like NGINX 👇

1️⃣ Round Robin
📌 What it does:
Distributes each new request to the next server in line, cycling through all available backends (pods).
🔁 How it works:
  • 1st request → Pod A
  • 2nd request → Pod B
  • 3rd request → Pod C
  • 4th request → Pod A again
... and so on.
✅ Pros:
  • Simple and fair.
  • Great when all pods have similar load capacity.
❌ Cons:
  • Doesn’t account for current load (e.g., one pod may be busier).

2️⃣ Least Connections
📌 What it does:
Sends requests to the pod with the fewest active connections.
📉 How it works:
  • Tracks how many active (in-flight) requests each pod has.
  • Routes new requests to the least busy pod.
✅ Pros:
  • Better for long-running requests.
  • Dynamically balances based on real-time load.
❌ Cons:
  • Slightly more overhead (needs to track connections).
  • Not all ingress controllers support this out of the box.

3️⃣ IP Hash
📌 What it does:
Uses a hash of the client's IP address to always send requests to the same backend pod.
🔐 How it works:
  • Hash(IP) → assigns a pod.
  • All requests from that IP go to the same pod (as long as the pod is alive).
✅ Pros:
  • Helps with session persistence (sticky sessions).
  • Same user always hits the same pod — useful for caching.
❌ Cons:
  • Traffic may be uneven if certain IPs generate more load.
  • Fewer IPs = fewer hash buckets = imbalance.

🎯 Quick Comparison:
| Algorithm  | Load Awareness  | Sticky Sessions | Use Case Example |
|----|----|----|----|
| Round Robin | ❌ No   | ❌ No   | Simple balanced traffic |
| Least Connections  | ✅ Yes  | ❌ No  A | PIs with varying request durations |
| IP Hash | ❌ No   | ✅ Yes  C | hat apps, game servers, caching apps |

