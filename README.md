# My DevOps Journey: A Guide to Essential Concepts

## Introduction
DevOps is a practice that integrates development and operations to improve collaboration, automate processes, and deliver software faster and more reliably. This guide highlights the core topics I’ve explored in DevOps and their practical applications.

## What I’ve Learned in DevOps
**1. Containerization vs. Virtualization:**
 - Containerization (e.g., Docker) provides lightweight, isolated environments for applications, whereas virtualization uses virtual machines with their own OS, making them heavier.
 - Improves **scalability** and **efficiency**, crucial for modern microservices architectures.

**2. Docker:**
 - Docker simplifies application packaging and deployment by creating consistent environments across development, testing, and production.
 - Provides featues such as **image layering**, **volume management**, and **networking**.

**3. Kubernetes:**
 - A container orchestration tool that manages the deployment, scaling, and operation of containers in clusters.
 - Features like **service discovery**, **load balancing**, and **self-healing** ensure high availability.

**4. Cloud Cost Optimization:**
 - Techniques like **autoscaling**, using **reserved instances**, and **monitoring cloud usage** help reduce operational costs while maintaining performance.

**5. EKS and Terraform:**
 - **EKS:** Amazon Elastic Kubernetes Service simplifies Kubernetes cluster management in AWS.
 - **Terraform:** An **Infrastructure as Code (IaC)** tool that enables declarative resource provisioning and management, ensuring **consistency**.

**6. Policy as Code:**
 - Enforcing organizational policies in code form (e.g., Open Policy Agent) ensures **compliance** and **security** in automated pipelines.

**7. Infrastructure as Code (IaC):**
 - Tools like Terraform or AWS CloudFormation allow defining infrastructure in code, making deployments **repeatable**, **scalable**, and **version-controlled**.

## Blog Summaries
### Blog 1: A Beginner’s Guide to Item-Based Collaborative Filtering
This blog explains item-based collaborative filtering, a technique used in recommendation systems. Unlike user-based filtering, it compares item similarities using metrics like Pearson Correlation, Cosine Similarity, and Adjusted Cosine Similarity. The choice of metric depends on factors like data sparsity and computational efficiency. The method calculates item similarities, identifies similar items, and recommends them based on user interactions.

### Blog 2: What are Kubernetes Secrets?
This blog explores Kubernetes Secrets, a secure way to store sensitive data like API keys, passwords, and certificates in containerized applications. It explains how to create, access, and manage Secrets in Kubernetes, while emphasizing best practices such as limiting access, using environment variables, and rotating Secrets regularly. Advanced topics include Secret lifecycle management and security audits.

##  Practical Application: Putting DevOps into Action
Now that we've explored the foundational concepts of DevOps, it's time to see how they come together in a real-world application. Consider deploying a Dockerized application on Kubernetes with Infrastructure as Code (IaC) using Terraform and EKS.

### Example Workflow:
1. Containerize your app using Docker.
2. Deploy the app to a Kubernetes cluster on EKS.
3. Use Terraform to provision the infrastructure automatically.
5. Implement Kubernetes Secrets to store sensitive information, like API keys, securely.

### Steps to Implement the Workflow:
**1. Setup Infrastructure:**
 - Write a Terraform configuration to provision an EKS cluster.
 - Add a GitHub Action step to initialize and apply the Terraform configuration.

**2. Build and Push Docker Images:**
 - Use a GitHub Action to build the Docker image for your app and push it to a container registry (e.g., Docker Hub or Amazon ECR).

**3. Deploy to Kubernetes:**
 - Use kubectl in your Action workflow to deploy the application manifest to the EKS cluster.
 - Include a step to apply Kubernetes Secrets securely.

**4. Monitor and Verify:**
 - Add steps to validate the deployment, such as ensuring Pods are running and services are exposed.

By automating these steps, you ensure a seamless, repeatable process for deploying applications, which is at the heart of DevOps practices. Code for automating the deployment of a sample Angular application has been made folder. It can be found in '.github/workflows' in the provided repository. This YAML code sets up a GitHub Actions workflow for building and deploying an Angular app with a merge and commit pipeline. Here's what it does:

**1. Trigger:** Runs on pull requests targeting the main branch when created or updated.
**2. Environment:** Runs on the latest Ubuntu environment.
**3. Steps:**
 - Checkout: Pulls the repository code.
 - Setup Node.js: Installs Node.js (version 18.13).
 - Install Dependencies: Runs npm install.
 - Run Tests: Executes tests using npm test.
 - Build Project: Compiles the Angular app using npm run build.
 - Merge PR: Automatically merges the PR if all steps pass.
 - Commit: Adds additional changes (e.g., formatting) and pushes them.

This workflow streamlines testing, building, and merging pull requests into the main branch.
