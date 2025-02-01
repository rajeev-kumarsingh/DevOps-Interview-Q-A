# EC2 Questions & Answer

# AWS EC2 Interview Questions and Answers (For 2 Years Experience)

## 🔹 Basic Level Questions (0-2 Years Experience)

### 1. What is Amazon EC2?

✅ **Answer:**  
Amazon **Elastic Compute Cloud (EC2)** is a web service that provides resizable cloud-based virtual servers. It enables users to run applications without managing physical servers.

---

### 2. What are the different EC2 instance types?

✅ **Answer:**  
EC2 instances are categorized into five types:

1. **General Purpose** – Balanced compute, memory, and networking (e.g., `t3`, `m5`)
2. **Compute Optimized** – High CPU performance (e.g., `c5`, `c6g`)
3. **Memory Optimized** – For memory-intensive workloads (e.g., `r5`, `x1e`)
4. **Storage Optimized** – For high disk throughput (e.g., `i3`, `d2`)
5. **Accelerated Computing** – GPU-based instances (e.g., `p4`, `inf1`)

---

### 3. What are AMIs (Amazon Machine Images)?

✅ **Answer:**  
An **AMI (Amazon Machine Image)** is a pre-configured virtual machine template that includes:

- **Operating System** (e.g., Ubuntu, Amazon Linux)
- **Pre-installed software** (e.g., Apache, MySQL)
- **Security permissions**

You can launch multiple EC2 instances from the same AMI.

---

### 4. What is the difference between a Security Group and a Network ACL?

✅ **Answer:**

| Feature              | Security Group                | Network ACL                   |
| -------------------- | ----------------------------- | ----------------------------- |
| **Level**            | Instance level                | Subnet level                  |
| **Rules Applied**    | Stateful                      | Stateless                     |
| **Inbound Traffic**  | Allowed if explicitly allowed | Default: Deny all             |
| **Outbound Traffic** | Allowed by default            | Requires explicit allow rules |

---

### 5. What is the difference between On-Demand, Reserved, and Spot Instances?

✅ **Answer:**

| Instance Type | Pricing             | Best For                              |
| ------------- | ------------------- | ------------------------------------- |
| **On-Demand** | Pay per hour/second | Short-term workloads                  |
| **Reserved**  | Up to 75% discount  | Long-term use (1-3 years)             |
| **Spot**      | Up to 90% discount  | Batch processing, fault-tolerant apps |

---

### 6. What is an Elastic IP Address?

✅ **Answer:**  
An **Elastic IP** is a static public IPv4 address that can be assigned to an EC2 instance. It remains the same even if the instance is stopped or restarted.

⚠ **Note:** AWS **charges for Elastic IPs** that are allocated but not in use.

---

### 7. How do you connect to an EC2 instance?

✅ **Answer:**

- **Linux:**
  ```bash
  ssh -i my-key.pem ec2-user@<public-ip>
  ```
- **Windows:** Use **RDP** with the Administrator password.

---

## 🔹 Intermediate Level Questions (2-4 Years Experience)

### 8. How do you resize an EC2 instance?

✅ **Answer:**

1. **Stop** the EC2 instance
2. Go to **EC2 Console → Instance Settings → Change Instance Type**
3. Choose a **new instance type**
4. **Start** the instance

⚠ **Important:** If the new instance type requires a different **virtualization type**, you may need to create a new AMI.

---

### 9. What is Auto Scaling in EC2?

✅ **Answer:**  
**Auto Scaling** allows EC2 instances to automatically scale **up** or **down** based on demand.

**Key Components:**

- **Launch Template** – Defines the instance configuration
- **Auto Scaling Group (ASG)** – Manages EC2 instances
- **Scaling Policy** – Increases/decreases instances based on CPU/memory usage

---

### 10. How do you back up an EC2 instance?

✅ **Answer:**

1. **EBS Snapshot** – Creates a backup of a volume
   ```bash
   aws ec2 create-snapshot --volume-id vol-12345678 --description "My Backup"
   ```
2. **Amazon Machine Image (AMI)** – Creates a reusable image
3. **AWS Backup** – Automates backups

---

### 11. What is the difference between Instance Store and EBS?

✅ **Answer:**

| Feature            | Instance Store                           | EBS (Elastic Block Store)     |
| ------------------ | ---------------------------------------- | ----------------------------- |
| **Persistence**    | **Temporary** (data lost on stop/reboot) | **Persistent** (data remains) |
| **Performance**    | Very high                                | High but slightly slower      |
| **Backup Support** | No                                       | Yes (EBS snapshots)           |

---

### 12. How does AWS EC2 pricing work?

✅ **Answer:**  
EC2 costs depend on:

- **Instance type** (CPU, RAM)
- **Billing Model** (On-Demand, Reserved, Spot)
- **Storage (EBS, instance store)**
- **Networking (Data transfer in/out of AWS)**
- **Elastic IP usage**

---

### 13. What happens when you stop vs. terminate an EC2 instance?

✅ **Answer:**

| Action        | Effect                                                                       |
| ------------- | ---------------------------------------------------------------------------- |
| **Stop**      | Data on **EBS persists**, IP may change                                      |
| **Terminate** | Instance **deleted permanently**, storage lost (unless EBS is set to retain) |

---

## 🔹 Advanced Level Questions (4+ Years Experience)

### 14. How do you troubleshoot an unreachable EC2 instance?

✅ **Answer:**

1. **Check instance status** in AWS Console
2. **Verify Security Groups & NACLs**
3. **Check Route Table** for correct routing
4. **Use AWS Systems Manager Session Manager** if SSH is blocked
5. **Review instance logs** (`/var/log/`)

---

### 15. What is a placement group in EC2?

✅ **Answer:**  
Placement groups determine **how instances are deployed**:

- **Clustered** – High-performance, low-latency (e.g., HPC apps)
- **Spread** – Instances spread across hardware for redundancy
- **Partitioned** – Large distributed applications (e.g., HDFS, Cassandra)

---

### 16. How do you configure EC2 User Data?

✅ **Answer:**  
User Data allows you to run scripts at **instance launch**.

Example (Apache web server installation on Linux):

```bash
#!/bin/bash
yum update -y
yum install httpd -y
systemctl start httpd
systemctl enable httpd
```

---

## Final Tips for Your AWS EC2 Interview

✅ **Practice AWS CLI commands** (`aws ec2 describe-instances`, `aws ec2 start-instances`)
✅ **Understand Security Groups, IAM roles, and permissions**
✅ **Be prepared to troubleshoot common EC2 issues**
✅ **Discuss real-world EC2 use cases**

#

# AWS EC2 Mock Interview Questions & Terraform Setup

## 🔹 Mock Interview Questions (For 2 Years Experience)

### **Basic Level**

1. **What is Amazon EC2, and how does it differ from traditional servers?**  
   ✅ **Answer:** Amazon Elastic Compute Cloud (EC2) is a cloud-based virtual server that provides scalable computing capacity. Unlike traditional servers, EC2 instances can be launched, stopped, or terminated as needed, and you pay only for what you use.

2. **What are the different EC2 instance types?**  
   ✅ **Answer:** EC2 instances are categorized into:

   - General Purpose (e.g., `t3`, `m5`)
   - Compute Optimized (e.g., `c5`, `c6g`)
   - Memory Optimized (e.g., `r5`, `x1e`)
   - Storage Optimized (e.g., `i3`, `d2`)
   - Accelerated Computing (e.g., `p4`, `inf1`)

3. **What is an AMI (Amazon Machine Image)?**  
   ✅ **Answer:** An AMI is a pre-configured virtual machine template containing the OS, software, and configurations needed to launch EC2 instances.

4. **Explain the difference between Security Groups and Network ACLs.**  
   ✅ **Answer:**

   - Security Groups operate at the **instance level** and are **stateful**.
   - Network ACLs operate at the **subnet level** and are **stateless**.
   - Security Groups allow only explicitly defined traffic, while Network ACLs can allow or deny rules for inbound and outbound traffic.

5. **How do you connect to an EC2 instance?**  
   ✅ **Answer:**
   - **Linux:** `ssh -i my-key.pem ec2-user@<public-ip>`
   - **Windows:** Use **RDP** with the Administrator password.

### **Intermediate Level**

6. **How do you resize an EC2 instance?**  
   ✅ **Answer:** You can stop the instance, change the instance type via the AWS Management Console or CLI, and restart it.

7. **What is Auto Scaling, and how does it work?**  
   ✅ **Answer:** Auto Scaling automatically adjusts the number of EC2 instances based on demand, ensuring high availability and cost efficiency.

8. **Explain the difference between Instance Store and EBS.**  
   ✅ **Answer:** Instance Store is temporary storage that is lost when an instance stops. EBS is persistent block storage that remains even after the instance is stopped or terminated.

9. **What are Placement Groups, and when should you use them?**  
   ✅ **Answer:** Placement Groups optimize instance placement for high network throughput or low latency. Types include Cluster, Partition, and Spread.

### **Advanced Level**

10. **How do you troubleshoot an unreachable EC2 instance?**  
    ✅ **Answer:** Steps to troubleshoot:

    - Verify Security Group rules (port 22 for SSH, RDP for Windows).
    - Check Network ACLs and Route Tables.
    - Use AWS System Manager Session Manager if SSH is unavailable.
    - Review instance console logs and CloudWatch logs.

11. **What is a Load Balancer, and what are the different types in AWS?**  
    ✅ **Answer:** A Load Balancer distributes traffic across multiple EC2 instances. Types include:

    - Application Load Balancer (ALB) – Layer 7 routing.
    - Network Load Balancer (NLB) – Layer 4, ultra-low latency.
    - Classic Load Balancer (CLB) – Older version, Layer 4/7.

12. **How would you secure an EC2 instance?**  
    ✅ **Answer:** Best practices include:

    - Restrict Security Group access.
    - Use IAM roles for permissions.
    - Enable MFA for AWS accounts.
    - Regularly patch and update OS.

13. **How do you set up a high-availability EC2 architecture?**  
    ✅ **Answer:**
    - Deploy instances across multiple **Availability Zones (AZs)**.
    - Use **Elastic Load Balancer (ELB)**.
    - Implement **Auto Scaling Groups**.
    - Store data in **EFS or RDS Multi-AZ**.

---

## 🔹 Terraform Configuration for EC2, VPC, Security Group, and Load Balancer

### **Terraform `main.tf` File**

```hcl
provider "aws" {
  region = "us-east-1"
}

resource "aws_vpc" "my_vpc" {
  cidr_block = "10.0.0.0/16"
}

resource "aws_subnet" "my_subnet" {
  vpc_id            = aws_vpc.my_vpc.id
  cidr_block        = "10.0.1.0/24"
  availability_zone = "us-east-1a"
}

resource "aws_security_group" "my_sg" {
  vpc_id = aws_vpc.my_vpc.id

  ingress {
    from_port   = 22
    to_port     = 22
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }

  ingress {
    from_port   = 80
    to_port     = 80
    protocol    = "tcp"
    cidr_blocks = ["0.0.0.0/0"]
  }
}

resource "aws_instance" "my_ec2" {
  ami           = "ami-12345678"  # Replace with a valid AMI ID
  instance_type = "t2.micro"
  subnet_id     = aws_subnet.my_subnet.id
  security_groups = [aws_security_group.my_sg.name]
}

resource "aws_lb" "my_lb" {
  name               = "my-load-balancer"
  internal           = false
  load_balancer_type = "application"
  security_groups    = [aws_security_group.my_sg.id]
  subnets            = [aws_subnet.my_subnet.id]
}
```

### **Steps to Deploy**

1. **Initialize Terraform**
   ```sh
   terraform init
   ```
2. **Validate Configuration**
   ```sh
   terraform validate
   ```
3. **Plan Deployment**
   ```sh
   terraform plan
   ```
4. **Apply Configuration**
   ```sh
   terraform apply -auto-approve
   ```

---

This Terraform script sets up an **EC2 instance, VPC, Security Group, and Load Balancer** in AWS. Let me know if you need custom modifications! 🚀
