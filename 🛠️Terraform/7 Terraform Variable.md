
# 📘 **Terraform Variables 


---

## ⭐ **1. Input Variables (`variable`)**

Used to pass values **into** Terraform.

```hcl
variable "environment" {
  default = "dev"
  type    = string
}
```

Use them as:

```
var.environment
```

---

## ⭐ **2. Output Variables (`output`)**

Used to **print/export values** after resources are created.

Example:

```hcl
output "vpc_id" {
  value = aws_vpc.sample.id
}
```

View output anytime:

```
terraform output
```

---

## ⭐ **3. Local Variables (`locals`)**

Used for **internal calculation**, concatenation, and reusable values.

```hcl
locals {
  bucket_name = "${var.project}-bucket-${var.environment}"
}
```

Use as:

```
local.bucket_name
```

---

#  Types of Variables (Based on Value / Type Constraints)

- **Primitive Types** — string, number, bool
- **Complex Types** — list(), set(), map(), object(), tuple()
- **Special Types** — any, null

---

# How to Set Variable Values (Precedence Order)

From **lowest → highest priority**:

1️⃣ **Default value inside variable block**

```hcl
default = "dev"
```

2️⃣ **Environment variable**

```
export TF_VAR_environment=stage
```

3️⃣ *_terraform.tfvars / _.auto.tfvars__

```hcl
environment = "preprod"
```

4️⃣ **-var flag (highest priority)**

```
terraform plan -var="environment=prod"
```

👉 **Last one wins** (overrides everything else).

#  Best Practices

✔ Use **variables.tf** → store all input variables  
✔ Use **local.tf** → store locals  
✔ Use **outputs.tf** → store outputs  
✔ Use **terraform.tfvars** for environment-specific values  
✔ Never hard-code secrets in variables → use SSM / Secrets Manager  


---

#  Summary 

- **Input variables** take values
- **Local variables** compute reusable values
- **Output variables** export values
- Many ways to set values → precedence decides final value
- Use variables to avoid repetition & support multi-environment deployment
