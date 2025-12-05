### What is Terraform?

- Terraform = **Infrastructure as Code (IaC)** tool by HashiCorp.
- Lets you **provision, change, and manage** cloud resources using `.tf` files.
- Supports **multi-cloud**, on-prem, SaaS, Kubernetes, etc.
- Declarative → you **describe the final state**, Terraform figures out _how_ to reach it.

### How Terraform Works

Write Terraform files → Run Terraform commands → Call AWS APIs through Terraform Provider

**Terraform Workflow Phases:**

1. `terraform init` - Initialize (downloads provider plugin)
2. `terraform validate` - Validate the configuration files
3. `terraform plan` -  compares the `.tf` config with the current state and shows **what will be created/changed/destroyed** to make desired state ( does not call API to create resources )
4. `terraform apply` - Apply the changes to reach desired state (actually makes API calls) 
5. `terraform destroy` - Destroy the infrastructure when needed

