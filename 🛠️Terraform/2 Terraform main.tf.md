
---
## 📁 main.tf

```
.
└── main.tf
    ├── terraform {}   → write providers in it
    ├── provider {}    → auth / region
    ├── resource {}    → resources to create (S3, VPC, EC2)
    ├── data {}        → Read-only info from cloud e.g ami_id
    ├── variable {}    → inputs
    └── output {}      → outputs
```

---
## 🟧 Data Source

→ Read-only lookups
→ Fetch info, don’t create

Example:

```hcl
data "aws_ami" "latest" {
  most_recent = true
  owners      = ["amazon"]
}
```

---

## 🟦 Lambda Packaging (archive_file)

### Structure

```
.
├── main.tf
└── lambda/
    └── handler.py
```

### Package Code → ZIP

```hcl
data "archive_file" "lambda_zip" {
  type        = "zip"
  source_dir  = "${path.module}/lambda"
  output_path = "${path.module}/lambda.zip"
}
```

### Use ZIP in Lambda

```hcl
resource "aws_lambda_function" "my_lambda" {
  function_name = "demo-lambda"
  role          = aws_iam_role.lambda_role.arn
  handler       = "handler.lambda_handler"
  runtime       = "python3.12"

  filename         = data.archive_file.lambda_zip.output_path
  source_code_hash = data.archive_file.lambda_zip.output_base64sha256
}
```

---

## 🟨 State File (`terraform.tfstate`)

→ Terraform’s memory  
→ Stores IDs, attributes  

Must be:
- **Protected**
- **Not edited manually**
- **Stored remotely** (S3 + DynamoDB lock recommended)

---

## 🟪 Variables

→ Avoid hardcoding

```hcl
variable "region" {
  default = "us-east-1"
}
```

---

## 🟫 Outputs

→ Print useful info

```hcl
output "vpc_id" {
  value = aws_vpc.main.id
}
```
