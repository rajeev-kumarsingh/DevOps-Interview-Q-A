# AWS CodePipeline Interview Questions and Answers

## Basic Level

### 1. **What is AWS CodePipeline?**

**Answer:**  
AWS CodePipeline is a fully managed continuous integration and continuous delivery (CI/CD) service that helps automate the build, test, and deployment phases of your release process.

### 2. **What are the key components of AWS CodePipeline?**

**Answer:**

- **Pipeline:** The workflow structure.
- **Stage:** Logical grouping of actions (e.g., Source, Build, Deploy).
- **Action:** Specific tasks performed (e.g., code compilation, tests).
- **Artifact:** Outputs produced by actions and passed between stages.

### 3. **How does AWS CodePipeline work?**

**Answer:**  
CodePipeline automates the software release process using stages that contain actions. Each action is performed in sequence or in parallel, allowing smooth transitions from source to deployment.

### 4. **What are the benefits of using CodePipeline?**

**Answer:**

- Automation of release processes
- Easy integration with AWS services
- Faster delivery with continuous deployment
- Customizable workflows

### 5. **What types of source repositories can CodePipeline integrate with?**

**Answer:**

- AWS CodeCommit
- GitHub/GitHub Enterprise
- Bitbucket
- Amazon S3

## Intermediate Level

### 6. **Explain the workflow of a typical CI/CD pipeline using AWS CodePipeline.**

**Answer:**

1. **Source Stage:** Code is pulled from repositories like CodeCommit or GitHub.
2. **Build Stage:** Code is compiled and built using AWS CodeBuild.
3. **Test Stage:** Automated tests are run.
4. **Deploy Stage:** The application is deployed using services like AWS CodeDeploy, ECS, or Lambda.

### 7. **What is a pipeline artifact in AWS CodePipeline?**

**Answer:**  
Artifacts are files generated during the pipeline execution, such as build outputs, deployment packages, or configuration files, passed between stages.

### 8. **How do you secure AWS CodePipeline?**

**Answer:**

- Use IAM roles with least privilege
- Enable encryption for artifacts
- Use secure connections (HTTPS, SSH)
- Audit with AWS CloudTrail

### 9. **Can CodePipeline trigger pipelines automatically?**

**Answer:**  
Yes, CodePipeline can trigger automatically based on source changes (like a Git push) or using AWS CloudWatch Events.

### 10. **What is the difference between CodePipeline and Jenkins?**

**Answer:**

- **CodePipeline:** Fully managed, integrated with AWS services, less customizable.
- **Jenkins:** Open-source, highly customizable, requires self-management.

## Advanced Level

### 11. **How do you handle rollback in AWS CodePipeline?**

**Answer:**

- Implement manual or automated approval actions
- Use AWS CodeDeploy with automatic rollback on failure
- Maintain versioned artifacts for easy rollback

### 12. **How do you integrate third-party tools with AWS CodePipeline?**

**Answer:**  
Using custom actions and AWS Lambda functions to connect tools like JIRA, Slack, or security scanners.

### 13. **What are approval actions in CodePipeline?**

**Answer:**  
Manual approval actions pause the pipeline, requiring human intervention before proceeding to the next stage.

### 14. **Explain how CodePipeline handles parallel execution.**

**Answer:**  
Within a stage, multiple actions can run in parallel. Stages, however, execute sequentially.

### 15. **How do you monitor AWS CodePipeline?**

**Answer:**

- AWS CloudWatch for metrics and alarms
- AWS CloudTrail for auditing
- CodePipeline console for real-time status

---

This document covers key AWS CodePipeline interview questions tailored for candidates with 2 years of experience. Customize answers based on your hands-on experience to make them more impactful.
