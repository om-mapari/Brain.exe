
AMI (Amazon Machine Image)
is a template used to create EC2 instances.
Ex. GitLab AMI include full GitLab stack (Rails app, PostgreSQL, Redis, etc.) pre-configured.

It contains all the information required to launch an instance:
\- OS 🖥️
\- App server 🛠️
\- App 📦
\- configurations and data 🧩

🧰 Types of AMIs
\- AWS-Provided AMIs – Standard Linux/Windows OS with base configuration.
\- Marketplace AMIs – AMIs provided by third-party vendors.
\- Community AMIs  – Public AMIs shared by AWS users.
\- Custom AMIs    – Created by you, customized to fit your app needs.

⚙️ Create an AMI
You can create an AMI from: 🖥️➕📸
\- An existing EC2 instance
\- A snapshot of a EBS volume - it will create snapshot :)
After Creating AMI Can be shared with: Specific AWS acc or Public

