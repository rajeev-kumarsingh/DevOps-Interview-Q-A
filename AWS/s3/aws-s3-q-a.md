# AWS S3 Interview Questions and Answers

## **Basic Level S3 Interview Questions and Answers**

### **Q1: What is Amazon S3?**

**Answer:**  
Amazon S3 (Simple Storage Service) is a scalable **object storage** service that allows users to store and retrieve large amounts of data. It provides **high availability, durability, and security** for data storage.

### **Q2: What are the key features of S3?**

**Answer:**

- **Durability**: 99.999999999% (11 nines) durability
- **Availability**: 99.99% availability
- **Scalability**: Stores unlimited data
- **Security**: IAM roles, bucket policies, ACLs
- **Data Management**: Lifecycle policies, versioning, replication
- **Cost-Effectiveness**: Different storage classes

### **Q3: What is an S3 bucket?**

**Answer:**  
An S3 bucket is a **container** that stores objects (files). Each bucket has a globally unique name and can store unlimited objects.

### **Q4: How is data organized in S3?**

**Answer:**  
S3 follows a **flat structure** but simulates a folder hierarchy using **prefixes and delimiters**.

### **Q5: What is the maximum size of a single S3 object?**

**Answer:**  
The maximum size of a single object is **5TB**, but the maximum size for a **single upload** is **5GB**. To upload larger files, use **Multipart Upload**.

### **Q6: What are the different storage classes in S3?**

**Answer:**

1. **S3 Standard** – Frequently accessed data
2. **S3 Intelligent-Tiering** – Automatically moves data between frequent and infrequent access
3. **S3 Standard-IA (Infrequent Access)** – Cheaper, but retrieval cost applies
4. **S3 One Zone-IA** – Cheaper, but stored in a single availability zone
5. **S3 Glacier** – Archival storage, retrieval time in minutes to hours
6. **S3 Glacier Deep Archive** – Lowest cost, retrieval time in hours

### **Q7: What is the difference between S3 and EBS?**

**Answer:**

- **S3** is **object storage** (for storing unstructured data like images, logs, backups).
- **EBS** is **block storage** (used for EC2 instances as a disk).

### **Q8: How do you secure an S3 bucket?**

**Answer:**

- Use **Bucket Policies**
- Use **IAM Policies**
- Enable **MFA Delete**
- Disable **Public Access**
- Enable **Encryption (SSE, KMS)**

### **Q9: How do you make an S3 bucket public?**

**Answer:**

1. Remove **Block Public Access** settings.
2. Set up **Bucket Policy** to allow public read access.
3. Enable **Object ACLs** (if needed).

## **Intermediate Level S3 Interview Questions and Answers**

### **Q10: What is S3 Versioning?**

**Answer:**  
S3 Versioning **keeps multiple versions** of an object to prevent accidental deletion. It helps with recovery in case of unintended modifications.

### **Q11: What is an S3 Lifecycle Policy?**

**Answer:**  
S3 Lifecycle Policy **automatically moves objects** between storage classes or deletes them after a certain period. Example: Move data from **Standard → Glacier** after 30 days.

### **Q12: What is Cross-Region Replication (CRR)?**

**Answer:**  
CRR replicates objects from **one S3 bucket to another in a different AWS region** for **disaster recovery and compliance**.

### **Q13: What is Same-Region Replication (SRR)?**

**Answer:**  
SRR replicates objects between **buckets in the same AWS region**, mainly for **backup and compliance**.

### **Q14: What is Pre-Signed URL in S3?**

**Answer:**  
A **Pre-Signed URL** provides **temporary access** to private S3 objects without making the bucket public. It is useful for **secure file downloads/uploads**.

### **Q15: What are S3 Event Notifications?**

**Answer:**  
S3 can trigger events when objects are created, updated, or deleted. These notifications can be sent to:

- **SNS (Simple Notification Service)**
- **SQS (Simple Queue Service)**
- **AWS Lambda (for processing)**

## **Expert Level S3 Interview Questions and Answers**

### **Q21: How does S3 ensure 99.999999999% (11 nines) durability?**

**Answer:**  
S3 **stores multiple copies** of objects across multiple Availability Zones (AZs) using **automated data replication**.

### **Q22: What happens when you delete an object in S3 with versioning enabled?**

**Answer:**  
Instead of deletion, S3 creates a **delete marker**. The object can be restored by removing the delete marker.

### **Q23: What is Object Lock in S3?**

**Answer:**  
Object Lock **prevents deletion** of objects for a defined period, helping in **compliance and data retention**.

### **Q24: How do you optimize S3 costs?**

**Answer:**

- Use **Lifecycle Policies** to move objects to cheaper storage classes.
- Enable **S3 Intelligent-Tiering**.
- Use **Glacier** for archival data.
- Compress files before uploading.

### **Q25: Can you host a website on S3? How?**

**Answer:**  
Yes, you can host a **static website** on S3 by:

1. Enabling **Static Website Hosting** on the bucket.
2. Uploading **HTML, CSS, and JavaScript** files.
3. Configuring **Bucket Policy** for public access.

### **Q26: What is the difference between Bucket Policy and IAM Policy?**

**Answer:**

- **Bucket Policy** applies to the **entire bucket**.
- **IAM Policy** applies to specific **users, groups, or roles**.

### **Q27: What is the maximum number of S3 buckets you can create per AWS account?**

**Answer:**  
By default, you can create **100 buckets per AWS account**, but you can request a limit increase.

### **Q28: Can S3 host a dynamic website?**

**Answer:**  
No, S3 only supports **static websites**. For dynamic content, use **EC2 or AWS Lambda with API Gateway**.

### **Q29: How do you troubleshoot slow S3 performance?**

**Answer:**

- **Use S3 Transfer Acceleration**
- **Optimize object size**
- **Enable CloudFront caching**
- **Use Multipart Upload for large files**

### **Q30: How can you monitor S3 bucket activity?**

**Answer:**

- **CloudTrail**: Logs API requests
- **CloudWatch Metrics**: Monitors storage usage
- **S3 Server Access Logs**: Logs all requests
