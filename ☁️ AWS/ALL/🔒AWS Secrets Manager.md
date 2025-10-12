
*🔐 AWS Secrets Manager - Secret Rotation Notes:*

*1️⃣ AWS Secrets Manager Secret Rotation Overview*
- 🔒 Secrets Manager helps securely store and manage secrets (e.g., database credentials).
- 🔄 It can automatically rotate secrets to enhance security.
- 🏗️ Rotation is implemented using an AWS Lambda function.
- 🔢 The process consists of four steps executed sequentially.

*2️⃣ Secret Versions and Labels*
- 🏷 AWSCURRENT: The currently active secret version.
- 🏷 AWSPENDING: The new secret version being created and tested during rotation.
- 🏷 AWSPREVIOUS: The last active secret before the most recent rotation.
- 🏷 AWS automatically assigns version labels to keep track of the secret lifecycle.

*3️⃣ Understanding ClientRequestToken (Version ID)*
- 🔑 ClientRequestToken is passed to the Lambda function during rotation.
- 🔄 It is the same as the Version ID for the new secret version.
- 🆔 Used to uniquely identify a specific rotation cycle.
- 🔁 Remains the same across all four rotation steps.

*📌 How to Check Version ID (Token)?*
aws secretsmanager describe-secret --secret-id \<SECRET_ARN\>
✅ Example Output:
{
  "VersionIdsToStages": {
    "1234abcd-5678-efgh-9101-ijklmnopqrst": \["AWSPENDING"\]
  }
}
🆔 Version ID: \`1234abcd-5678-efgh-9101-ijklmnopqrst\` (Same as ClientRequestToken).

*4️⃣ Secret Rotation Process Steps*
- *Step 1: createSecret*
  - AWS automatically assigns \`AWSPENDING\` to the new version.
  - The Lambda function generates a new password and stores it as \`AWSPENDING\`.

- 📝 Code:

secret = secrets_client.get_secret_value(SecretId=secret_arn, VersionStage="AWSCURRENT")

new_password = generate_random_password()

secrets_client.put_secret_value(

SecretId=secret_arn,

ClientRequestToken=token,

SecretString=json.dumps(new_secret_dict),

VersionStages=\["AWSPENDING"\]

)

- *Step 2: setSecret*
  - Updates the DocumentDB user password with the new secret from \`AWSPENDING\`.
  - 📝 Code:

client = pymongo.MongoClient(

f"mongodb://{secret_dict\['username'\]}:{secret_dict\['password'\]}@{secret_dict\['host'\]}:{secret_dict\['port'\]}/?ssl=true&retryWrites=false",

tls=True,

tlsAllowInvalidCertificates=True

)

db.command("updateUser", secret_dict\["username"\], pwd=secret_dict\["password"\])

- *Step 3: testSecret*
  - ✅ Validates the new credentials by attempting to connect to DocumentDB.
  - Runs a simple \`ping\` command.
  - 📝 Code: db.command("ping")

- *Step 4: finishSecret*
  - 🔀 Promotes the \`AWSPENDING\` version to \`AWSCURRENT\`.
  - 📝 Code:
secrets_client.update_secret_version_stage(

SecretId=secret_arn,

VersionStage="AWSCURRENT",

MoveToVersionId=token

)

*5️⃣ Key Takeaways 🎯*
- ✅ ClientRequestToken = Version ID (Unique for each rotation cycle).
- ✅ Same token is used in all four steps of rotation.
- ✅ AWS automatically handles version staging (\`AWSPENDING\` → \`AWSCURRENT\`).
- ✅ Rotation ensures secrets are periodically refreshed for security.
- ✅ Secrets Manager provides built-in integration with AWS Lambda.

*6️⃣ Why Use the Admin_Clone Practice? 🤔*
🎯 Purpose: The \`admin_clone\` practice is used to create a temporary user with the same permissions as the admin user.
- 🔎 Reason:
  - 🚨 Reduces the risk of directly modifying admin credentials.
  - 🔄 Ensures a smooth rotation process without impacting critical system operations.
  - ♻️ Allows rollback in case of failure since the original admin credentials remain unchanged.

- 🛠️ How It Works:
  - 🆕 A temporary user (\`admin_clone\`) is created using the \`createUser\` command.
  - 🔄 The new credentials are rotated and tested before being promoted.
  - ✅ Once verified, the \`admin_clone\` replaces the old admin user.
  - ❌ The old admin user is then either revoked or deleted.

*7️⃣ Additional Notes 📝*
- ⏳ AWS recommends setting rotation intervals (e.g., every 30 days).
- 🔑 IAM permissions must allow the Lambda function to access Secrets Manager & DocumentDB.
- 📊 Logs can be monitored in AWS CloudWatch for debugging issues.

- 🚀 This structured summary should help you revise AWS Secrets Manager rotation efficiently! 🔥
