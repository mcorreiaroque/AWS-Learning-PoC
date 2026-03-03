# Section 4: IAM - Identity and Access Management

## IAM Fundamentals (Lectures 14 - 20)
* **Global Service:** IAM is a global service; you do not select a specific region.
* **Root Account:** Created by default. Should only be used for initial account setup. **Never** share or use it for daily tasks.
* **Users:** Physical users mapped to an individual. They have a password for the AWS Console.
* **Groups:** A collection of users. Permissions are applied to the group, and all users in that group inherit them.
* **Multi-Factor Authentication (MFA):** Adds an extra layer of security. Options include Virtual MFA (Apps), U2F Security Keys (USB), or Hardware Key Fobs.

## IAM Policies (Lectures 17 & 18)
* **JSON Documents:** Policies are JSON documents that define permissions.
* **Policy Structure:**
    * **Effect:** Allow or Deny.
    * **Action:** The API call being allowed/denied (e.g., `s3:ListBucket`).
    * **Resource:** The specific AWS resource the action applies to.
* **Principle of Least Privilege:** Don't give more permissions than a user strictly needs to perform their job.

## IAM Roles (Lectures 27 - 28)
* **Definition:** Roles are intended to be assumed by **AWS services** (like an EC2 instance) instead of physical users.
* **Use Case:** Grant permissions to an EC2 instance so it can access other AWS resources (e.g., an S3 bucket) on your behalf.

## Accessing AWS (Lectures 21 - 26)
* **Access Keys:** Credentials used for programmatic access via CLI or SDK.
* **AWS CLI:** Tool to manage AWS services using command-line instructions.
* **AWS SDK:** Libraries to manage AWS services using a programming language.
* **AWS CloudShell:** A browser-based shell accessible directly from the AWS Console.

## Security & Audit Tools (Lectures 29 - 30)
* **IAM Credential Report (Account-level):** Lists all users in your account and the status of their credentials.
* **IAM Access Advisor (User-level):** Shows permissions granted and when services were last accessed to help audit "Least Privilege".

## IAM Best Practices (Lecture 31)
* **Don't use the root account** for daily tasks.
* **One physical user = One IAM user**.
* **Assign permissions to Groups**, not individual users.
* **Use Strong Password Policies** and enforce **MFA**.
* **Use IAM Roles** for providing permissions to AWS services.
* **Audit often** using Credential Reports and Access Advisor.