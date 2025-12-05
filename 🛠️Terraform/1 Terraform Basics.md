
![[../attachments/1 Terraform Basics.webp|675]]

## 🟦 Provider

- Talks to cloud APIs
- Required in every config
- Installed via: `terraform init`
### Types

→ **Official**    maintained by hashicorp (AWS, Azure, GCP) 
→ **Partner**   Heroku & digital ocean
→ **Community**   open source

registry.terraform.io - registry name
hashicorp/local - provider name 

### Versioning

→ Two versions: Terraform CLI + Provider  
→ Pin versions to avoid breakage

### Constraints

`=`, `!=`, `<`, `<=`, `>=`, `>`, `~>`

Examples:

- `~> 6.7.0` → 6.7.x
- `~> 1.0` → 1.x.x (not 2.0)

**Block**

```hcl
terraform {
  required_providers {
    aws = {
      source  = "hashicorp/aws"
      version = "~> 6.0"
    }
  }
}

provider "aws" {
  region = "us-east-1"
}
```

---
