# AWS Certification Cheat Sheet

_Last updated: June 2025_

**More cheatsheets:** [Cloudoku Training Cheatsheets](https://cloudoku.training/cheatsheets)

---

## Table of Contents

- [1. Compute Services](#1-compute-services)
- [2. Storage Services](#2-storage-services)
- [3. Database Services](#3-database-services)
- [4. Networking & Content Delivery](#4-networking--content-delivery)
- [5. Security, Identity & Compliance](#5-security-identity--compliance)
- [6. Analytics & Machine Learning](#6-analytics--machine-learning)
- [7. Developer Tools & Management](#7-developer-tools--management)
- [8. Migration & Transfer](#8-migration--transfer)
- [9. Application Integration](#9-application-integration)
- [10. Cost Management & Optimization](#10-cost-management--optimization)
- [11. Best Practices and Tips](#11-best-practices-and-tips)
- [12. Preparing for AWS Certifications](#12-preparing-for-aws-certifications)

---

## 1. Compute Services

### **Amazon EC2 (Elastic Compute Cloud)**
- **Purpose:** Resizable virtual servers in the cloud.
- **Instance Types:** General Purpose (`t3`, `m5`), Compute Optimized (`c5`), Memory Optimized (`r5`), GPU (`p3`, `g4`)
- **Pricing Models:** On-Demand, Reserved, Spot, Dedicated Hosts
- **Key Features:** Auto Scaling, Elastic Load Balancing, Elastic IPs, Security Groups
- **Example:**
    ```sh
    aws ec2 run-instances --image-id ami-12345678 --count 1 --instance-type t3.micro
    ```
- **Exam Tip:** Know when to use each instance type/pricing model.

---

### **AWS Lambda**
- **Purpose:** Run code without provisioning/managing servers (serverless).
- **Supported Languages:** Node.js, Python, Java, C#, Go, Ruby, custom runtimes
- **Common Triggers:** API Gateway, S3 events, DynamoDB streams, CloudWatch Events
- **Example:**
    ```sh
    aws lambda create-function --function-name MyFunction \
      --runtime python3.8 \
      --role arn:aws:iam::123456789012:role/service-role/MyTestFunction-role-abc123 \
      --handler lambda_function.lambda_handler \
      --zip-file fileb://function.zip
    ```
- **Exam Tip:** Lambda billing is per ms of execution time.

---

### **Amazon Elastic Beanstalk**
- **Purpose:** PaaS for easy deployment and management of web apps.
- **Supported Platforms:** Java, .NET, PHP, Node.js, Python, Ruby, Go, Docker
- **Features:** Auto Scaling, load balancing, health monitoring

---

### **Amazon ECS & EKS**
- **ECS:** AWS-managed Docker container orchestration.
- **EKS:** AWS-managed Kubernetes clusters.
- **Fargate:** Serverless compute engine for containers.
- **Use Cases:** Microservices, containerized workloads

---

### **AWS Batch**
- **Purpose:** Managed batch computing for large-scale parallel/HPC workloads.
- **Use Case:** Scientific simulations, financial modeling, genomics

---

### **AWS Outposts**
- **Purpose:** Extend AWS infrastructure/services to on-premises for hybrid cloud.

---

## 2. Storage Services

### **Amazon S3 (Simple Storage Service)**
- **Purpose:** Object storage for any amount of data from anywhere.
- **Storage Classes:** Standard, Intelligent-Tiering, Standard-IA, One Zone-IA, Glacier, Glacier Deep Archive
- **Features:** 11 nines durability, lifecycle policies, versioning, encryption
- **Use Cases:** Backup, static hosting, analytics, media hosting
- **Example:**
    ```sh
    aws s3 cp file.txt s3://mybucket/
    ```
- **Exam Tip:** Know when to use each storage class.

---

### **Amazon EBS (Elastic Block Store)**
- **Purpose:** Persistent block storage for EC2.
- **Volume Types:** gp3/gp2 (SSD), io1/io2 (Provisioned IOPS), st1 (Throughput HDD), sc1 (Cold HDD)
- **Use Cases:** Boot volumes, databases, low-latency apps

---

### **Amazon EFS (Elastic File System)**
- **Purpose:** Scalable file storage for Linux workloads.
- **Features:** Scales automatically, supports NFS, multi-AZ replication

---

### **Amazon FSx**
- **Purpose:** Managed Windows or Lustre file systems.

---

### **AWS Storage Gateway**
- **Purpose:** Hybrid storage bridging on-premises software with cloud storage.

---

## 3. Database Services

### **Amazon RDS (Relational Database Service)**
- **Purpose:** Managed relational DBs (MySQL, PostgreSQL, Oracle, SQL Server, Aurora)
- **Features:** Automated backups, Multi-AZ, read replicas

---

### **Amazon Aurora**
- **Purpose:** High-performance, MySQL/PostgreSQL-compatible relational DB.
- **Advantage:** Up to 5x faster than standard MySQL

---

### **Amazon DynamoDB**
- **Purpose:** Managed, serverless NoSQL DB with key-value/document models.
- **Features:** Single-digit ms latency, auto scaling, global tables

---

### **Amazon ElastiCache**
- **Purpose:** Managed in-memory data store (Redis/Memcached)

---

### **Amazon Neptune**
- **Purpose:** Managed graph database for highly connected data

---

### **Amazon DocumentDB**
- **Purpose:** Managed document DB compatible with MongoDB

---

### **Amazon Timestream**
- **Purpose:** Scalable time-series database for IoT/operations

---

## 4. Networking & Content Delivery

### **Amazon VPC (Virtual Private Cloud)**
- **Purpose:** Create isolated virtual networks, subnets, route tables, gateways
- **Features:** Public/private subnets, NAT gateways, VPC peering, VPNs
- **Tip:** Use private subnets for sensitive workloads

---

### **Elastic Load Balancing (ELB)**
- **Types:** Application (HTTP/HTTPS), Network (TCP/UDP), Gateway
- **Use Cases:** High availability, scaling, fault tolerance

---

### **Amazon Route 53**
- **Purpose:** Highly available DNS service
- **Features:** DNS routing, health checks, domain registration

---

### **Amazon CloudFront**
- **Purpose:** CDN for low-latency global delivery of static/dynamic content

---

### **AWS Direct Connect**
- **Purpose:** Dedicated network connection from premises to AWS

---

### **AWS Global Accelerator**
- **Purpose:** Improves global application availability/performance

---

## 5. Security, Identity & Compliance

### **AWS IAM (Identity and Access Management)**
- **Purpose:** Control access to AWS resources via users, groups, roles, policies
- **Best Practices:** Least privilege, MFA, use roles for EC2/Lambda

---

### **AWS Organizations & SCPs**
- **Purpose:** Manage multiple AWS accounts; apply governance guardrails

---

### **AWS KMS (Key Management Service)**
- **Purpose:** Create/manage encryption keys

---

### **AWS CloudTrail & AWS Config**
- **CloudTrail:** Logs API calls for auditing
- **Config:** Monitors resource configurations for compliance

---

### **AWS Shield & WAF**
- **Shield:** DDoS protection
- **WAF:** Protects against web exploits

---

## 6. Analytics & Machine Learning

### **Amazon Athena**
- **Purpose:** Serverless interactive queries on S3 using SQL

---

### **Amazon EMR (Elastic MapReduce)**
- **Purpose:** Managed Hadoop/Spark clusters for big data processing

---

### **Amazon Kinesis**
- **Purpose:** Real-time data streaming & analytics

---

### **Amazon SageMaker**
- **Purpose:** Build, train, deploy ML models at scale

---

### **AI Services**
- **Examples:** Comprehend (NLP), Rekognition (image/video), Polly (text-to-speech), Lex (chatbots)

---

## 7. Developer Tools & Management

### **AWS CloudFormation**
- **Purpose:** Define infrastructure as code for provisioning resources
- **Example:**
    ```yaml
    Resources:
      MyBucket:
        Type: AWS::S3::Bucket
    ```

---

### **AWS CloudTrail**
- **Purpose:** Audit AWS API calls for security/compliance

---

### **Amazon CloudWatch**
- **Purpose:** Monitor metrics, logs, set alarms

---

### **AWS CodeCommit, CodeBuild, CodeDeploy, CodePipeline**
- **Purpose:** End-to-end CI/CD pipeline services

---

### **AWS Systems Manager**
- **Purpose:** Automate ops tasks, patch management, run commands

---

## 8. Migration & Transfer

### **AWS Snow Family**
- **Purpose:** Transfer large volumes of data into AWS

---

### **AWS Database Migration Service (DMS)**
- **Purpose:** Migrate DBs to AWS with minimal downtime

---

### **AWS Server Migration Service (SMS)**
- **Purpose:** Automate migration of on-premises workloads to AWS

---

## 9. Application Integration

### **Amazon SQS (Simple Queue Service)**
- **Purpose:** Managed message queues to decouple microservices

---

### **Amazon SNS (Simple Notification Service)**
- **Purpose:** Pub/sub messaging for notifications

---

### **Amazon EventBridge**
- **Purpose:** Serverless event bus for application integration

---

### **AWS Step Functions**
- **Purpose:** Serverless orchestration of workflows

---

## 10. Cost Management & Optimization

- **AWS Cost Explorer:** Visualize and analyze AWS spend
- **AWS Budgets:** Set custom cost/usage budgets
- **AWS Trusted Advisor:** Cost optimization recommendations
- **Savings Plans:** Flexible pricing to save compute costs

---

## 11. Best Practices and Tips

- Use **consistent tagging** for cost allocation/resource management
- Apply **least privilege** with IAM
- Enable **multi-factor authentication (MFA)**
- Automate **backups, snapshots, disaster recovery**
- Monitor with **CloudWatch** and set alarms proactively
- Leverage **Auto Scaling** for cost/performance optimization

---

## 12. Preparing for AWS Certifications

- Build a clear study plan, hands-on practice, and take mock exams.
- Use Cloudoku’s [practice exams and cheatsheets](https://cloudoku.training/cheatsheets).
- Follow study tips, review AWS whitepapers, practice regularly.

---

**Good luck on your AWS certification journey!**
