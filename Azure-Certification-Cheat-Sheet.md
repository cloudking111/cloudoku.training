# Azure Certification Cheat Sheet

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
- [8. Migration & Hybrid Cloud](#8-migration--hybrid-cloud)
- [9. Application Integration](#9-application-integration)
- [10. Cost Management & Optimization](#10-cost-management--optimization)
- [11. Best Practices and Tips](#11-best-practices-and-tips)
- [12. Preparing for Azure Certifications](#12-preparing-for-azure-certifications)

---

## 1. Compute Services

### **Azure Virtual Machines (VM)**
- **Purpose:** Scalable, on-demand Windows/Linux VMs.
- **VM Series:** General Purpose (B, D), Compute Optimized (F), Memory Optimized (E, M), Storage Optimized (L), GPU (NC, NV)
- **Pricing Models:** Pay-as-you-go, Reserved, Spot VMs, Dedicated Hosts
- **Key Features:** Auto-scaling, Availability Sets/Zones, Managed Disks, VM Scale Sets
- **Example (CLI):**
    ```sh
    az vm create --resource-group MyResourceGroup --name MyVM --image UbuntuLTS --generate-ssh-keys
    ```
- **Exam Tip:** Know VM sizes, pricing, and high-availability options.

---

### **Azure App Service**
- **Purpose:** PaaS for hosting web apps, APIs, and mobile backends.
- **Supported Stacks:** .NET, Node.js, Java, Python, PHP, Ruby, Docker
- **Features:** Auto-scaling, deployment slots, custom domains, SSL, CI/CD integration

---

### **Azure Functions**
- **Purpose:** Serverless compute to run event-driven code.
- **Triggers:** HTTP, Timer, Blob, Queue, Event Grid, Event Hub, Service Bus
- **Example (CLI):**
    ```sh
    az functionapp create --resource-group MyResourceGroup --consumption-plan-location westus --runtime python --functions-version 4 --name MyFunctionApp --storage-account mystorageacct
    ```
- **Exam Tip:** Billing is per execution and resource consumption.

---

### **Azure Kubernetes Service (AKS)**
- **Purpose:** Fully managed Kubernetes clusters.
- **Features:** Integrated monitoring, scaling, Azure AD integration, Windows/Linux nodes
- **Use Cases:** Microservices, containerized workloads

---

### **Azure Batch**
- **Purpose:** Managed batch and parallel computing workloads.

---

## 2. Storage Services

### **Azure Blob Storage**
- **Purpose:** Object storage for unstructured data.
- **Tiers:** Hot, Cool, Archive
- **Features:** Lifecycle management, versioning, encryption, soft delete
- **Example (CLI):**
    ```sh
    az storage blob upload --account-name mystorageacct --container-name mycontainer --name file.txt --file ./file.txt
    ```
- **Exam Tip:** Know when to use each access tier.

---

### **Azure Disk Storage**
- **Purpose:** Persistent block storage for VMs.
- **Types:** Standard HDD/SSD, Premium SSD, Ultra Disk

---

### **Azure Files**
- **Purpose:** Fully managed file shares accessible via SMB/NFS.

---

### **Azure Data Lake Storage**
- **Purpose:** Scalable storage for big data analytics.

---

### **Azure Storage Account**
- **Purpose:** Unified management for Blob, File, Queue, Table storage.

---

## 3. Database Services

### **Azure SQL Database**
- **Purpose:** Managed relational SQL database (PaaS).
- **Features:** Scaling, geo-replication, automated backups, threat detection

---

### **Azure Cosmos DB**
- **Purpose:** Globally distributed NoSQL database (multi-model).
- **APIs:** SQL, MongoDB, Cassandra, Gremlin, Table
- **Features:** Multi-region writes, automatic failover, low-latency

---

### **Azure Database for MySQL/PostgreSQL/MariaDB**
- **Purpose:** Managed open-source relational databases.
- **Features:** High availability, automated patching/backups

---

### **Azure Cache for Redis**
- **Purpose:** In-memory cache for high throughput/low-latency data

---

### **Azure Database Migration Service**
- **Purpose:** Migrate databases to Azure with minimal downtime

---

## 4. Networking & Content Delivery

### **Azure Virtual Network (VNet)**
- **Purpose:** Provision private networks, subnets, route tables, gateways
- **Features:** Network Security Groups (NSG), VNet Peering, Service Endpoints

---

### **Azure Load Balancer**
- **Types:** Public, Internal
- **Features:** Layer 4 (TCP, UDP) load balancing

---

### **Azure Application Gateway**
- **Purpose:** Layer 7 (HTTP/HTTPS) load balancer with WAF

---

### **Azure DNS**
- **Purpose:** Host DNS domains, manage DNS records

---

### **Azure Content Delivery Network (CDN)**
- **Purpose:** Global caching for low-latency content delivery

---

### **Azure ExpressRoute**
- **Purpose:** Dedicated private network connection to Azure

---

## 5. Security, Identity & Compliance

### **Azure Active Directory (Azure AD)**
- **Purpose:** Identity and access management (IAM)
- **Features:** SSO, MFA, Conditional Access, B2B/B2C

---

### **Azure Key Vault**
- **Purpose:** Secure storage for secrets, keys, certificates

---

### **Azure Security Center (Defender for Cloud)**
- **Purpose:** Posture management, threat protection, security recommendations

---

### **Azure Policy**
- **Purpose:** Governance and compliance for resources

---

### **Azure DDoS Protection & Firewall**
- **Purpose:** Protect against DDoS attacks and manage network traffic

---

## 6. Analytics & Machine Learning

### **Azure Synapse Analytics**
- **Purpose:** Big data analytics, data warehousing, and integration

---

### **Azure Data Factory**
- **Purpose:** Data integration, ETL, and orchestration

---

### **Azure Databricks**
- **Purpose:** Apache Spark-based analytics platform

---

### **Azure Machine Learning**
- **Purpose:** Build, train, and deploy ML models at scale

---

### **Azure Cognitive Services**
- **Purpose:** Prebuilt AI for vision, speech, language, decision

---

## 7. Developer Tools & Management

### **Azure Resource Manager (ARM) Templates**
- **Purpose:** Infrastructure as Code (IaC) for resource deployment
- **Example:**
    ```json
    {
      "$schema": "https://schema.management.azure.com/schemas/2019-04-01/deploymentTemplate.json#",
      "contentVersion": "1.0.0.0",
      "resources": [
        {
          "type": "Microsoft.Storage/storageAccounts",
          "apiVersion": "2021-02-01",
          "name": "mystorageacct",
          "location": "eastus",
          "sku": { "name": "Standard_LRS" },
          "kind": "StorageV2",
          "properties": {}
        }
      ]
    }
    ```

---

### **Azure Monitor**
- **Purpose:** Monitor metrics, logs, set alerts, visual dashboards

---

### **Azure DevOps Services**
- **Purpose:** CI/CD pipelines, repos, boards, artifacts

---

### **Azure Automation**
- **Purpose:** Automate tasks, patch management, update management

---

## 8. Migration & Hybrid Cloud

### **Azure Migrate**
- **Purpose:** Discover, assess, and migrate on-premises workloads

---

### **Azure Site Recovery**
- **Purpose:** Disaster recovery as a service (DRaaS)

---

### **Azure Arc**
- **Purpose:** Manage on-premises and multi-cloud resources from Azure

---

## 9. Application Integration

### **Azure Logic Apps**
- **Purpose:** Automate workflows and integrate apps/data

---

### **Azure Service Bus**
- **Purpose:** Reliable cloud messaging (queues/topics)

---

### **Azure Event Grid**
- **Purpose:** Event routing for serverless architectures

---

### **Azure Event Hubs**
- **Purpose:** Big data streaming platform and event ingestion

---

## 10. Cost Management & Optimization

- **Azure Cost Management + Billing:** Analyze and optimize cloud spend
- **Azure Advisor:** Personalized cloud best practices and recommendations
- **Azure Reservations:** Pre-pay for resources to save costs
- **Azure Pricing Calculator:** Estimate costs before deployment

---

## 11. Best Practices and Tips

- Use **resource tagging** for management and cost allocation
- Apply **least privilege** and enable **MFA**
- Automate **backups and disaster recovery**
- Monitor with **Azure Monitor** and set alerts
- Leverage **auto-scaling** for performance/cost balance

---

## 12. Preparing for Azure Certifications

- Build a study plan, get hands-on with the Azure Portal and CLI, use sandbox/labs
- Take Cloudoku’s [practice exams and cheatsheets](https://cloudoku.training/cheatsheets)
- Review Microsoft Learn modules, whitepapers, and practice exams

---

**Good luck on your Azure certification journey!**
