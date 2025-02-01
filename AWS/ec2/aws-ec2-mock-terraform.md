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

6. **What are the different pricing models for EC2 instances?**  
   ✅ **Answer:**

   - **On-Demand**: Pay per hour/second, best for short-term workloads.
   - **Reserved**: Discounted pricing for long-term commitments (1-3 years).
   - **Spot Instances**: Cheapest option, but instances may be terminated if demand increases.

7. **What happens when you stop or terminate an EC2 instance?**  
   ✅ **Answer:**
   - **Stopping** retains the instance with its EBS volume but deallocates the computing resources.
   - **Terminating** deletes the instance and its attached volumes (unless configured otherwise).

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
