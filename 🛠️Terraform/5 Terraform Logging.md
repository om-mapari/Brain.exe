
---

# 🔵 **Terraform Diff Symbols (VERY IMPORTANT)**

Terraform shows diffs like this:

```
+ create
~ update in-place
- destroy
-/+ replace
<= read (data source)
```

Let’s break them down:

---

## ✔ **`+` Create**

Terraform will create a resource.

Example:

```
# aws_lambda_function.put will be created
+ resource "aws_lambda_function" "put" {
```

Meaning:  
Resource **does NOT exist** in AWS → Terraform will create it.

---

## ✔ **`~` Update In-Place**

Resource exists but needs modification.

```
~ memory_size: 128 → 256
```

Meaning:  
Terraform will update the resource **without deleting it**.

---

## ✔ **`-` Destroy**

Terraform will delete a resource.

```
- resource "aws_lambda_function" "old"
```

Meaning:  
Terraform thinks this resource should _not_ exist.

---

## ✔ **`-/+` Replace**

Resource must be **destroyed then recreated**.

```
-/+ resource "aws_lambda_function" "example"
```

Meaning:  
Some attributes **force replacement**, like:
- function name


Terraform will:  
1️⃣ destroy  
2️⃣ recreate

---

## ✔ **`<=` Read**

This is for **data sources**.

```
<= data "aws_ami" "latest"
```

Meaning:  
Terraform is reading data (not creating anything).

---

# 🟧 **Plan Summary (bottom section)**

At the bottom of `terraform plan`, you always see:

```
Plan: 3 to add, 1 to change, 0 to destroy
```

This is your **quick summary**.

---

# 🔵**Terraform Logs (TF_LOG)**

Terraform has **internal debug logs** beyond CLI output.

You enable them using environment variables:

---

## 🔥 Debug Levels

```
TF_LOG=ERROR
TF_LOG=WARN
TF_LOG=INFO
TF_LOG=DEBUG
TF_LOG=TRACE
```

Example:

```bash
export TF_LOG=DEBUG
terraform plan
```

### Meaning:

- `ERROR` = only fatal failures
    
- `WARN` = warnings
    
- `INFO` = lifecycle messages
    
- `DEBUG` = provider communication details
    
- `TRACE` = very deep details (API requests, JSON, diff engine)
    

---

# 📁 **3️⃣ TF_LOG_PATH — Save logs to a file**

Instead of printing to terminal:

```bash
export TF_LOG=DEBUG
export TF_LOG_PATH="terraform.log"

terraform apply
```

Now all logs go into:

```
terraform.log
```

---
