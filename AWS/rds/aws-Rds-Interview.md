# AWS RDS Interview Questions and Answers

## **Basic Level RDS Interview Questions and Answers**

### **Q1: What is Amazon RDS?**

**Answer:**  
Amazon RDS (Relational Database Service) is a managed database service that simplifies setting up, operating, and scaling relational databases in the cloud.

### **Q2: What are the benefits of using Amazon RDS?**

**Answer:**

- Automated backups and snapshots
- Multi-AZ deployments for high availability
- Read replicas for performance improvements
- Security with encryption and IAM policies
- Automated software patching
- Scalability with vertical and horizontal scaling

### **Q3: Which database engines does RDS support?**

**Answer:**

- Amazon Aurora
- MySQL
- PostgreSQL
- MariaDB
- Oracle
- Microsoft SQL Server

### **Q4: What is an RDS instance?**

**Answer:**  
An RDS instance is a virtual machine that hosts the database engine and provides storage, CPU, memory, and networking for database operations.

### **Q5: What is the maximum size of an RDS database?**

**Answer:**  
The maximum size depends on the database engine, but Amazon Aurora supports up to **128 TB**, while other engines support up to **64 TB**.

### **Q6: What are the different storage types available in RDS?**

**Answer:**

- **General Purpose SSD (gp2/gp3)** – Balanced cost and performance
- **Provisioned IOPS SSD (io1/io2)** – High-performance workloads
- **Magnetic (Deprecated)** – Legacy storage option

### **Q7: What is Multi-AZ Deployment in RDS?**

**Answer:**  
Multi-AZ deployment provides **high availability** by maintaining a **standby replica** in a different Availability Zone (AZ) and automatically failing over during outages.

### **Q8: What are Read Replicas in RDS?**

**Answer:**  
Read Replicas allow **scaling read operations** by creating **read-only copies** of the primary database in the same or different AWS regions.

### **Q9: How does RDS handle backups?**

**Answer:**  
RDS provides two types of backups:

1. **Automated Backups** – Enabled by default, allows point-in-time recovery.
2. **Manual Snapshots** – User-initiated and stored indefinitely.

### **Q10: What is the default backup retention period in RDS?**

**Answer:**  
The default backup retention period is **7 days**, but it can be configured between **0 to 35 days**.

## **Intermediate Level RDS Interview Questions and Answers**

### **Q11: What is Amazon Aurora?**

**Answer:**  
Amazon Aurora is a **high-performance, managed relational database** that is compatible with MySQL and PostgreSQL, offering **5x the performance of MySQL**.

### **Q12: What are the benefits of using Amazon Aurora over RDS?**

**Answer:**

- **Faster performance (5x MySQL, 3x PostgreSQL)**
- **Storage auto-scaling up to 128 TB**
- **Replication with Aurora Replicas**
- **Continuous backups and point-in-time recovery**

### **Q13: What is IAM database authentication in RDS?**

**Answer:**  
IAM authentication allows users to connect to RDS without passwords by using IAM roles and tokens.

### **Q14: How do you encrypt RDS data?**

**Answer:**

- **Encryption at Rest:** Using AWS KMS (Key Management Service).
- **Encryption in Transit:** Using SSL/TLS connections.

### **Q15: What happens during an RDS failover?**

**Answer:**  
During a failover in a Multi-AZ setup:

1. The standby instance is promoted to primary.
2. DNS is updated to point to the new primary instance.
3. The old primary becomes the new standby.

### **Q16: Can you change the instance type of an RDS instance?**

**Answer:**  
Yes, you can **modify** an RDS instance to change its instance type, but it requires **downtime** during the process.

### **Q17: What are the differences between RDS and DynamoDB?**

**Answer:**  
| Feature | RDS (Relational DB) | DynamoDB (NoSQL) |
|---------------|-----------------|----------------|
| Data Model | Structured (SQL) | Key-Value & Document (NoSQL) |
| Scaling | Vertical & Read Replicas | Fully managed horizontal scaling |
| Performance | Fixed instance sizes | On-demand scaling |
| Use Case | OLTP applications | High-throughput, low-latency apps |

### **Q18: What is Enhanced Monitoring in RDS?**

**Answer:**  
Enhanced Monitoring provides **real-time OS-level metrics** such as CPU, memory, disk I/O, and network activity.

### **Q19: How do you improve RDS performance?**

**Answer:**

- Enable **Read Replicas** for scaling.
- Use **Provisioned IOPS** for high workloads.
- Optimize **query performance** and indexing.
- Enable **Aurora if using MySQL or PostgreSQL**.

### **Q20: What is Performance Insights in RDS?**

**Answer:**  
Performance Insights helps identify **database bottlenecks** and provides insights into SQL query performance.

## **Expert Level RDS Interview Questions and Answers**

### **Q21: How do you migrate an on-premise database to RDS?**

**Answer:**

1. **Use AWS DMS (Database Migration Service)**.
2. **Manually export/import data** (via mysqldump, pg_dump, etc.).
3. **Use native database replication methods**.

### **Q22: How do you enable automatic failover in RDS?**

**Answer:**

- **Enable Multi-AZ deployment**.
- **Use Route 53 health checks** for DNS failover.

### **Q23: What is the difference between Multi-AZ and Read Replicas?**

**Answer:**  
| Feature | Multi-AZ | Read Replica |
|----------------|---------|--------------|
| Purpose | High availability | Performance improvement |
| Readable? | No | Yes |
| Automatic Failover | Yes | No |
| Used For | DR & failover | Read scaling |

### **Q24: How do you monitor RDS logs?**

**Answer:**

- **Amazon CloudWatch Logs**.
- **Enable database engine logs (error, slow query logs)**.

### **Q25: Can you stop an RDS instance?**

**Answer:**  
Yes, you can stop an RDS instance **for up to 7 days** to save costs.

### **Q26: What is Amazon RDS Proxy?**

**Answer:**  
RDS Proxy **optimizes database connections**, reduces overhead, and improves **scalability** for applications.

### **Q27: How does Amazon RDS handle patching?**

**Answer:**

- AWS **automatically applies patches** during maintenance windows.
- You can enable **auto minor version upgrades**.

### **Q28: How do you reduce RDS costs?**

**Answer:**

- **Use Reserved Instances** for long-term savings.
- **Turn off idle instances**.
- **Use Aurora Serverless for on-demand workloads**.
- **Enable automatic backups to avoid data loss**.

---

This **comprehensive list** covers **basic to expert-level** RDS questions for interviews. Let me know if you need modifications! 🚀
