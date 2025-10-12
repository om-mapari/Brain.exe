
🧠 Think of it as:
"The local ECS manager on each EC2 instance that talks to ECS, pulls task instructions, and manages the lifecycle of your containers."

The Brain Behind ECS on EC2
The Amazon ECS Agent is a software component that runs on EC2 instances in your ECS cluster (when using the EC2 launch type). It is responsible for managing the container lifecycle and communicating with the ECS control plane.

🔍 What Does the ECS Agent Do?
📡 Registers the EC2 instance with your ECS cluster.
📦 Pulls task definitions from ECS and launches containers accordingly.
📊 Reports the status of running tasks and the EC2 instance back to ECS.
🔄 Manages container lifecycle:
starting, stopping, and restarting containers as needed.
🪵 Streams logs and metrics (e.g., to Amazon CloudWatch).
🔐 Works with IAM roles for secure access to AWS services from your containers.

🖥️ How Does It Run?
🧱 On Amazon ECS-optimized AMIs, the ECS Agent runs as a native process on the host, not as a Docker container.
🐳 It can be run as a Docker container manually on other Linux AMIs with Docker installed, but that’s not typical for most users.
💡 In both setups, the agent manages Docker containers running on the EC2 instance.

📁 ECS Agent Logs & Debugging
| View ECS agent logs: | sudo cat /var/log/ecs/ecs-agent.log |
|----|----|
| Check ECS agent status and metadata: | curl <http://localhost:51678/v1/metadata> |
| Restart the ECS agent: | sudo systemctl restart ecs |

