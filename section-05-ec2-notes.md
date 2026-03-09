# Section 5: EC2 - Elastic Compute Cloud (Stephane Mareek)

## 1. EC2 Instance Fundamentals
*   **Definition:** Virtual server in the AWS cloud.
*   **Security Groups (Firewall):** 
    *   Control traffic to/from your instance.
    *   Default: All inbound traffic is blocked, all outbound is allowed.
    *   Changes take effect immediately.
*   **EC2 User Data:** 
    *   A bootstrapping script that runs **only at the first start** of an instance.
    *   Commonly used to automate updates, install software (like Apache), or download files.
*   **SSH (Secure Shell):** 
    *   Allows you to start a terminal/remote session into your Linux EC2 instances.
    *   Requires a Key Pair (`.pem` or `.ppk`).
*   **EC2 Instance Roles:** 
    *   Linked to IAM Roles.
    *   Grants the EC2 instance permission to access other AWS services (like S3) without needing to store credentials (access keys) on the instance.

## 2. EC2 Purchasing Options (Exam Critical!)
| Option | Best Use Case | Cost |
| :--- | :--- | :--- |
| **On-Demand** | Short-term, unpredictable workloads. No upfront payment. | High (highest cost) |
| **Reserved (Standard)** | Steady-state usage (1 or 3 years). | Up to 72% discount |
| **Reserved (Convertible)**| Can change EC2 instance type/family/OS. | Up to 54% discount |
| **Spot Instances** | Batch jobs, data analysis, resilient workloads. | Up to 90% discount (cheapest) |
| **Dedicated Hosts** | Compliance (bring your own license), physical server control. | Expensive |
| **Dedicated Instances** | Hardware dedicated to one customer (no sharing). | Expensive |

## 3. Key Concepts for the Quiz
*   **Instance Types:** M (General Purpose), C (Compute), R (RAM), I (I/O), G (GPU).
*   **EC2 Hibernate:** Saves RAM state to EBS (root volume); much faster boot.
*   **EBS (Elastic Block Store):** Network drive attached to EC2 for data persistence.
