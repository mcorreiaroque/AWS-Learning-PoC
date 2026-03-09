# Section 5: EC2 - Elastic Compute Cloud

## 1. EC2 Instance Fundamentals
*   **Definition:** Virtual server in the AWS cloud (IaaS).
*   **Security Groups (Firewall):** 
    *   Control traffic to/from your instance.
    *   **Stateful:** If you allow an inbound port, the outbound traffic is automatically allowed.
    *   **Default:** All inbound is blocked; all outbound is allowed.
    *   **Rules:** Can be filtered by IP range or by other Security Groups.
*   **EC2 User Data:** 
    *   Bootstrapping script that runs **only once** at the first launch.
    *   Used for automation (installing software, updates).

## 2. Instance Types (The "Naming" Cheat Sheet)
AWS uses a naming convention like `t2.micro`:
*   **t:** Family name.
*   **2:** Generation.
*   **micro:** Size within the family.

| Family | Type | Best For |
| :--- | :--- | :--- |
| **General Purpose** | **t, m** | Diversity of workloads (web servers, code repos). |
| **Compute Optimized** | **c** | Batch processing, media transcoding, high-perf web servers. |
| **Memory Optimized** | **r** | High-perf databases, real-time big data, in-memory caches. |
| **Storage Optimized** | **i, d, h**| Distributed file systems, data warehousing, high-frequency OLTP. |

## 3. AMI (Amazon Machine Image)
*   **Definition:** A template that contains the software configuration (OS, application server, applications) required to launch your instance.
*   **Custom AMIs:** You can build your own AMI for faster booting (software is pre-installed).
*   **Region-locked:** AMIs are specific to the region they were created in (but can be copied).

## 4. EC2 Storage: EBS vs. Instance Store
*   **EBS (Elastic Block Store):**
    *   Network drive (can be detached and moved).
    *   **Persistent:** Data survives instance termination (if configured).
    *   Can take **Snapshots** (backups) to S3.
*   **EC2 Instance Store:**
    *   Physical disk attached to the host server.
    *   **Ephemeral:** Data is **lost** if the instance is stopped or terminated.
    *   Highest I/O performance (good for temporary buffers/cache).

## 5. EC2 Purchasing Options
| Option | Best Use Case | Cost |
| :--- | :--- | :--- |
| **On-Demand** | Short-term, unpredictable. | Highest (Pay per second) |
| **Reserved (1 or 3 yrs)** | Long-term, steady-state usage. | Up to 72% discount |
| **Savings Plans** | Commitment to a dollar amount ($/hour). | Same as Reserved |
| **Spot Instances** | Flexible start/end times. **Can be lost if AWS needs capacity.** | Up to 90% discount (cheapest) |
| **Dedicated Hosts** | Physical servers; helps with specific BYOL licenses. | Most Expensive |

## 6. Shared Responsibility Model for EC2
*   **AWS:** Infrastructure, hardware, global network, host security (hypervisor).
*   **Customer:** Guest OS (security patches/updates), Application security, Data encryption, **Security Group rules**.
