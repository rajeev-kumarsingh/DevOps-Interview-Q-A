# GitLab CI/CD Pipeline Interview Questions and Answers

## Basic Level

### 1. **What is GitLab CI/CD?**

**Answer:**  
GitLab CI/CD is a built-in continuous integration and continuous deployment tool in GitLab that automates the process of building, testing, and deploying code.

### 2. **What is a GitLab Runner?**

**Answer:**  
A GitLab Runner is an application used to run jobs in a GitLab CI/CD pipeline. It can be configured to run on different environments like Docker, virtual machines, or physical servers.

### 3. **What is `.gitlab-ci.yml` file?**

**Answer:**  
The `.gitlab-ci.yml` file is used to define the CI/CD pipeline in GitLab. It contains the configuration of stages, jobs, scripts, and other pipeline-related settings.

### 4. **What are stages in GitLab CI/CD?**

**Answer:**  
Stages are phases in a CI/CD pipeline where specific tasks are executed. Common stages include **build**, **test**, and **deploy**.

### 5. **What are jobs in GitLab CI/CD?**

**Answer:**  
Jobs are individual tasks that run within stages. Each job defines what needs to be executed, like running tests or deploying code.

## Intermediate Level

### 6. **How does GitLab CI/CD work?**

**Answer:**  
When code is pushed to a repository, GitLab CI/CD automatically triggers a pipeline defined in the `.gitlab-ci.yml` file. The pipeline executes jobs across different stages using GitLab Runners.

### 7. **How do you trigger pipelines in GitLab?**

**Answer:**

- Automatically on code push or merge requests
- Manually via the GitLab UI
- Scheduled pipelines
- API triggers

### 8. **What are artifacts in GitLab CI/CD?**

**Answer:**  
Artifacts are files generated during a job, such as build outputs or test reports. They can be shared between jobs or downloaded for analysis.

### 9. **How do you handle dependencies between jobs?**

**Answer:**  
Dependencies are managed using **stages** and **job dependencies** (`needs` keyword) to control execution order and parallelism.

### 10. **What are shared and specific runners?**

**Answer:**

- **Shared Runners:** Available to all projects in GitLab.
- **Specific Runners:** Dedicated to a particular project or group.

## Advanced Level

### 11. **What is caching in GitLab CI/CD?**

**Answer:**  
Caching stores intermediate files to speed up subsequent pipeline runs. It reduces the need to download dependencies repeatedly.

### 12. **How do you implement environment-specific deployments in GitLab?**

**Answer:**  
Use the `environment` keyword in `.gitlab-ci.yml` to define environments like development, staging, and production. Deployments can be controlled using manual triggers or conditions.

### 13. **Explain the use of variables in GitLab CI/CD.**

**Answer:**  
Variables store dynamic values such as credentials, API keys, or configuration settings. They can be defined at the project, group, or pipeline level.

### 14. **How do you secure GitLab CI/CD pipelines?**

**Answer:**

- Use protected branches and tags
- Secure secrets using CI/CD variables
- Apply role-based access control (RBAC)
- Use secure runners

### 15. **What is GitLab Auto DevOps?**

**Answer:**  
Auto DevOps automates the entire CI/CD pipeline using predefined templates, enabling easy setup for building, testing, and deploying applications.

## Troubleshooting and Best Practices

### 16. **How do you troubleshoot failed GitLab pipelines?**

**Answer:**

- Check pipeline logs for errors
- Review `.gitlab-ci.yml` syntax and configurations
- Test commands locally
- Validate runner configurations

### 17. **What are some best practices for GitLab CI/CD?**

**Answer:**

- Keep pipelines simple and modular
- Use caching and artifacts effectively
- Secure sensitive data with environment variables
- Regularly update runners and GitLab versions

---

This document covers key GitLab CI/CD Pipeline interview questions tailored for candidates with 2 years of experience. Customize answers based on your hands-on experience to make them more impactful.
