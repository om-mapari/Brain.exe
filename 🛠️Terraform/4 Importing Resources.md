

---

# 📌 **How Import Works**

Import command:

```bash
terraform import <terraform_resource_address> <aws_resource_identifier>
```

After import:
- Terraform updates `terraform.tfstate`    
- But **does NOT write code for you*    
- You must have matching resource config in `.tf` files    

---

# 📌 **Example — Import IAM Role**

Terraform code:

```hcl
resource "aws_iam_role" "lambda_role" {
  name = "OrderUpLambdaExecutionRole"
}
```

Import:

```bash
terraform import aws_iam_role.lambda_role OrderUpLambdaExecutionRole
```

Now Terraform knows:  
“This existing IAM role belongs to this resource block.”

---

# 📌 **Important Rules**

✔ Resource MUST exist in AWS  
✔ Resource MUST exist as a block in Terraform  
✔ Import ONLY updates state, not your .tf code  
✔ After import: run `terraform plan`

---

# 📌 **Workflow Summary**

1. Write the resource block in `.tf`
2. Run `terraform import`
3. Run `terraform plan`
4. Fix any differences
5. Run `terraform apply`

