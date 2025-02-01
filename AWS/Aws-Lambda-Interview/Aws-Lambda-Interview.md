# AWS Lambda Interview Questions and Answers

## **Basic Level AWS Lambda Interview Questions and Answers**

### **Q1: What is AWS Lambda?**

**Answer:**  
AWS Lambda is a **serverless compute service** that allows you to run code without provisioning or managing servers. It automatically scales and executes code in response to events.

### **Q2: What are the main benefits of AWS Lambda?**

**Answer:**

- **Serverless** – No need to manage infrastructure.
- **Automatic scaling** – Scales based on demand.
- **Cost-effective** – Pay only for the execution time.
- **Event-driven** – Triggered by AWS services or HTTP requests.

### **Q3: What languages are supported by AWS Lambda?**

**Answer:**  
AWS Lambda supports the following languages:

- Python
- Node.js
- Java
- Go
- C# (.NET Core)
- Ruby
- PowerShell

### **Q4: How do you trigger an AWS Lambda function?**

**Answer:**  
AWS Lambda functions can be triggered by:

- **API Gateway** (HTTP requests)
- **S3 Events** (file uploads/deletions)
- **DynamoDB Streams**
- **SQS and SNS Messages**
- **CloudWatch Events and Logs**
- **Step Functions**
- **EventBridge**

### **Q5: What is the maximum execution time of a Lambda function?**

**Answer:**  
The maximum execution time for a Lambda function is **15 minutes**.

### **Q6: How does AWS Lambda handle scaling?**

**Answer:**  
AWS Lambda scales automatically by creating **multiple concurrent instances** of a function as demand increases.

### **Q7: What are the AWS Lambda pricing factors?**

**Answer:**  
AWS Lambda pricing is based on:

- **Number of requests** – First 1M requests are free, then $0.20 per million.
- **Execution time** – Charged per GB-second.
- **Provisioned Concurrency** (if enabled).

### **Q8: How do you secure AWS Lambda?**

**Answer:**

- Use **IAM roles and policies** for access control.
- Enable **VPC access** if required.
- Encrypt environment variables.
- Use **AWS Secrets Manager** to store sensitive data.

### **Q9: How do you deploy a Lambda function?**

**Answer:**  
AWS Lambda functions can be deployed using:

- AWS Console
- AWS CLI
- AWS SAM (Serverless Application Model)
- Terraform
- CloudFormation

### **Q10: What is the cold start issue in AWS Lambda?**

**Answer:**  
A **cold start** happens when a Lambda function is invoked after being inactive for a while, leading to a delay as the execution environment is initialized.

## **Intermediate Level AWS Lambda Interview Questions and Answers**

### **Q11: How do you optimize AWS Lambda performance?**

**Answer:**

- Reduce function size by using **smaller deployment packages**.
- Increase **memory allocation** to speed up execution.
- Use **Provisioned Concurrency** to avoid cold starts.
- Keep dependencies minimal.

### **Q12: What is Provisioned Concurrency in AWS Lambda?**

**Answer:**  
Provisioned Concurrency **pre-warms instances** of a Lambda function, reducing cold start latency.

### **Q13: What is the difference between AWS Lambda and EC2?**

**Answer:**  
| Feature | AWS Lambda | EC2 |
|---------|-----------|-----|
| Server Management | Fully managed | User-managed |
| Scalability | Automatic | Manual or Auto Scaling |
| Billing | Pay per request | Pay for uptime |
| Use Case | Event-driven applications | Persistent applications |

### **Q14: What is the maximum memory allocation for AWS Lambda?**

**Answer:**  
AWS Lambda allows memory allocation between **128MB to 10GB**.

### **Q15: How do you monitor AWS Lambda functions?**

**Answer:**

- **Amazon CloudWatch Logs** – Captures logs.
- **AWS X-Ray** – Traces requests.
- **CloudWatch Metrics** – Monitors performance.

### **Q16: What is AWS Lambda Layers?**

**Answer:**  
AWS Lambda Layers allow you to **package common dependencies** separately and reuse them across multiple functions.

### **Q17: How do you handle errors in AWS Lambda?**

**Answer:**

- **Try-Catch blocks** in code.
- **Dead Letter Queues (DLQ)** for failed executions.
- **AWS Step Functions** for retries and error handling.

### **Q18: What is the Lambda execution environment?**

**Answer:**  
AWS Lambda runs in a **sandboxed environment** with a runtime (Node.js, Python, etc.) inside an AWS-managed container.

### **Q19: How do you use AWS Lambda with API Gateway?**

**Answer:**  
API Gateway acts as an HTTP front-end for AWS Lambda, allowing it to be invoked via **REST API or WebSocket API**.

### **Q20: What is the difference between SQS and SNS in Lambda triggers?**

**Answer:**

- **SNS**: Push-based, triggers Lambda for each message.
- **SQS**: Pull-based, allows Lambda to batch process messages.

## **Expert Level AWS Lambda Interview Questions and Answers**

### **Q21: What is the maximum payload size for AWS Lambda?**

**Answer:**

- **Event payload**: 6MB for synchronous invocations.
- **S3-triggered events**: 256KB.
- **Asynchronous event queue**: 256KB.

### **Q22: How do you manage dependencies in AWS Lambda?**

**Answer:**

- **Use Lambda Layers** for common libraries.
- **Use container images** for large dependencies.
- **Package dependencies inside the deployment package**.

### **Q23: How does AWS Lambda integrate with Step Functions?**

**Answer:**  
AWS Step Functions orchestrate multiple AWS Lambda functions into a **workflow with retries, parallel execution, and state management**.

### **Q24: What are the retry strategies for failed Lambda executions?**

**Answer:**

- **Synchronous execution**: No retries by default.
- **Asynchronous execution**: Retries twice before sending to a Dead Letter Queue (DLQ).
- **Step Functions**: Custom retry policies.

### **Q25: What is the role of Dead Letter Queues (DLQ) in Lambda?**

**Answer:**  
DLQs capture **failed Lambda invocations**, enabling debugging and retry logic.

### **Q26: How do you run a Lambda function locally?**

**Answer:**

- Use **AWS SAM CLI (`sam local invoke`)**.
- Use **Docker for containerized Lambda functions**.

### **Q27: What is AWS Lambda@Edge?**

**Answer:**  
Lambda@Edge allows running AWS Lambda functions at **CloudFront edge locations** to modify requests and responses.

### **Q28: How do you set environment variables in AWS Lambda?**

**Answer:**

- Set via **AWS Console, CLI, or CloudFormation**.
- Use **AWS Secrets Manager** for sensitive values.

### **Q29: What are common use cases for AWS Lambda?**

**Answer:**

- **Real-time data processing** (e.g., IoT, logs, streaming data).
- **Automating infrastructure** (e.g., cron jobs, backups).
- **Event-driven applications** (e.g., image processing, notifications).

### **Q30: What are some AWS Lambda limitations?**

**Answer:**

- **15-minute execution time limit**.
- **Maximum memory: 10GB**.
- **Max request payload: 6MB**.

---

This **comprehensive list** covers **basic to expert-level** AWS Lambda interview questions. Let me know if you need modifications! 🚀
