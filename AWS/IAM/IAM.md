# AWS IAM Interview Questions and Answers

## **Basic Level IAM Interview Questions and Answers**

### **Q1: What is AWS IAM?**

**Answer:**  
AWS IAM (Identity and Access Management) is a service that allows you to securely control access to AWS resources by managing users, groups, roles, and permissions.

### **Q2: What are the key features of IAM?**

**Answer:**

- Centralized control of AWS accounts
- Granular permissions using policies
- Support for multi-factor authentication (MFA)
- Integration with AWS services
- Secure temporary access using IAM roles

### **Q3: What is an IAM user?**

**Answer:**  
An IAM user is an entity that represents a person or application that interacts with AWS resources.

### **Q4: What is an IAM role?**

**Answer:**  
An IAM role is an identity with specific permissions that can be assumed by trusted entities (users, applications, or AWS services) to access AWS resources.

### **Q5: What is the difference between an IAM user and an IAM role?**

**Answer:**  
| Feature | IAM User | IAM Role |
|---------|---------|---------|
| Authentication | Uses a username & password | Assumed by trusted entities |
| Permissions | Directly assigned | Uses policies attached to the role |
| Use Case | Individual access | Temporary access for applications or AWS services |

### **Q6: What are IAM policies?**

**Answer:**  
IAM policies are JSON documents that define permissions for users, groups, and roles to allow or deny access to AWS resources.

### **Q7: What types of IAM policies exist?**

**Answer:**

- **Managed Policies**: AWS-managed and customer-managed policies.
- **Inline Policies**: Directly attached to a single IAM user, group, or role.

### **Q8: What is an IAM group?**

**Answer:**  
An IAM group is a collection of IAM users that share the same permissions, simplifying access management.

### **Q9: What is the IAM root user?**

**Answer:**  
The IAM root user is the initial user created with an AWS account, having unrestricted access to all AWS resources.

### **Q10: What is AWS IAM MFA (Multi-Factor Authentication)?**

**Answer:**  
IAM MFA enhances security by requiring an additional authentication factor (such as OTP) apart from a username and password.

## **Intermediate Level IAM Interview Questions and Answers**

### **Q11: What are IAM roles used for?**

**Answer:**  
IAM roles are used to grant permissions to AWS services, applications, or federated users for accessing AWS resources securely.

### **Q12: How can you enforce MFA on an IAM user?**

**Answer:**

- Enable MFA via AWS Console or CLI.
- Attach an MFA-required policy to enforce MFA authentication.

### **Q13: What is an IAM access key?**

**Answer:**  
An IAM access key consists of an **Access Key ID** and a **Secret Access Key**, used for programmatic access to AWS resources.

### **Q14: How can you rotate IAM access keys?**

**Answer:**

- Create a new access key.
- Update applications to use the new key.
- Disable the old key and eventually delete it.

### **Q15: What is an IAM instance profile?**

**Answer:**  
An IAM instance profile is a container for an IAM role that allows EC2 instances to assume a role and obtain temporary credentials.

### **Q16: What is the principle of least privilege in IAM?**

**Answer:**  
The **principle of least privilege** means granting only the minimum permissions required for users, groups, and roles to perform their tasks.

### **Q17: What are service-linked roles in IAM?**

**Answer:**  
Service-linked roles are IAM roles predefined by AWS services to allow them to perform specific operations on behalf of the user.

### **Q18: How do you troubleshoot IAM access issues?**

**Answer:**

- Use **IAM Policy Simulator** to test permissions.
- Check CloudTrail logs for access denials.
- Verify policies and ensure no explicit denies.

### **Q19: What is AWS STS (Security Token Service)?**

**Answer:**  
AWS STS provides temporary security credentials for IAM users, roles, and federated users for secure access to AWS resources.

### **Q20: How do IAM roles differ from IAM policies?**

**Answer:**

- **IAM roles** define who can assume a role and what actions they can perform.
- **IAM policies** define permissions attached to roles, users, or groups.

## **Expert Level IAM Interview Questions and Answers**

### **Q21: What is the difference between identity-based and resource-based policies?**

**Answer:**  
| Policy Type | Description |
|-------------|-------------|
| Identity-Based Policy | Attached to IAM users, groups, or roles to control their actions. |
| Resource-Based Policy | Attached directly to AWS resources like S3 buckets to control who can access them. |

### **Q22: How does IAM integrate with AWS Organizations?**

**Answer:**  
AWS Organizations allows centralized management of multiple AWS accounts with **Service Control Policies (SCPs)** that limit IAM permissions at the account level.

### **Q23: How do you grant temporary access to an IAM user?**

**Answer:**

- Use **IAM roles with STS** to issue temporary credentials.
- Use **IAM access keys** with limited validity.

### **Q24: How do you implement least privilege access for AWS Lambda functions?**

**Answer:**

- Assign **minimal IAM permissions** to the Lambda execution role.
- Use **IAM condition keys** to restrict access.
- Regularly review and audit permissions.

### **Q25: How does IAM support cross-account access?**

**Answer:**  
Cross-account access is enabled using IAM roles and trust relationships, allowing users from one AWS account to access resources in another account.

### **Q26: How do you monitor IAM activities?**

**Answer:**

- **AWS CloudTrail** logs IAM activities.
- **AWS IAM Access Analyzer** detects misconfigured permissions.
- **AWS Config** audits IAM resources and changes.

### **Q27: What is the IAM policy evaluation logic?**

**Answer:**  
IAM policy evaluation follows these rules:

1. **Explicit Deny** – Denies access if any policy explicitly denies.
2. **Explicit Allow** – Grants access if an allow policy exists and no deny overrides.
3. **Implicit Deny** – Denies access by default unless explicitly allowed.

### **Q28: How do you revoke active IAM sessions?**

**Answer:**

- Use **AWS RevokeSession API**.
- Change or delete the IAM user's credentials.

### **Q29: What is AWS Identity Federation?**

**Answer:**  
AWS Identity Federation allows external identity providers (Google, Microsoft AD, etc.) to authenticate users and grant them temporary access to AWS resources.

### **Q30: How do you enforce password policies in IAM?**

**Answer:**  
AWS IAM allows setting **password policies** to enforce:

- Minimum password length
- Require uppercase, lowercase, numbers, and symbols
- Password expiration and reuse prevention

---

This **comprehensive list** covers **basic to expert-level** IAM interview questions. 🚀
