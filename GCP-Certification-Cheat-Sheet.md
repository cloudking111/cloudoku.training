# GCP Certification Cheat Sheet

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
- [12. Preparing for GCP Certifications](#12-preparing-for-gcp-certifications)

---

## 1. Compute Services

### **Compute Engine**
- **Purpose:** Scalable VMs in Google Cloud.
- **Machine Types:** E2, N2, N2D, C2, A2, custom
- **Pricing Models:** On-demand, preemptible, committed use, sole-tenant
- **Key Features:** Instance groups, autoscaling, live migration, custom images
- **Example (gcloud):**
    ```sh
    gcloud compute instances create my-vm --zone=us-central1-a --machine-type=e2-medium --image-family=debian-11 --image-project=debian-cloud
    ```
- **Exam Tip:** Understand sustained use discounts and preemptible VMs.

---

### **App Engine**
- **Purpose:** Fully managed PaaS for web apps.
- **Environments:** Standard (sandboxed), Flexible (custom runtimes)
- **Features:** Autoscaling, zero server management, traffic splitting

---

### **Cloud Functions**
- **Purpose:** Event-driven serverless functions.
- **Triggers:** HTTP, Pub/Sub, Cloud Storage, Firestore, etc.
- **Example (gcloud):**
    ```sh
    gcloud functions deploy myFunction --runtime python310 --trigger-http --allow-unauthenticated
    ```
- **Exam Tip:** Pay only for function execution time.

---

### **Cloud Run**
- **Purpose:** Serverless containers (run any language in Docker containers).
- **Features:** HTTP endpoints, auto-scale to zero, fully managed or Anthos

---

### **Google Kubernetes Engine (GKE)**
- **Purpose:** Managed Kubernetes clusters.
- **Features:** Node pools, auto-upgrades, auto-repair, integrates IAM

---

## 2. Storage Services

### **Cloud Storage**
- **Purpose:** Object storage for unstructured data.
- **Storage Classes:** Standard, Nearline, Coldline, Archive
- **Features:** Lifecycle management, versioning, uniform bucket-level access
- **Example (gsutil):**
    ```sh
    gsutil cp file.txt gs://mybucket/
    ```
- **Exam Tip:** Know when to use each storage class and their cost tradeoffs.

---

### **Persistent Disk**
- **Purpose:** Block storage for Compute Engine VMs.
- **Types:** Standard (HDD), Balanced/SSD, Extreme SSD, Local SSD

---

### **Filestore**
- **Purpose:** Managed NFS file storage for GKE, Compute Engine.

---

### **Transfer Service & Storage Transfer**
- **Purpose:** Move data into/out of GCP from cloud or on-prem.

---

## 3. Database Services

### **Cloud SQL**
- **Purpose:** Managed relational DB (MySQL, PostgreSQL, SQL Server).
- **Features:** Backups, failover, replicas, IAM integration

---

### **Cloud Spanner**
- **Purpose:** Horizontally scalable, strongly consistent relational DB.
- **Features:** Global transactions, automatic sharding, high availability

---

### **Firestore & Datastore**
- **Purpose:** NoSQL document DBs for web/mobile apps.
- **Features:** Real-time sync, offline mode, scalable

---

### **Bigtable**
- **Purpose:** NoSQL wide-column database for analytics, time series.

---

### **Memorystore**
- **Purpose:** Managed Redis/Memcached cache.

---

### **BigQuery**
- **Purpose:** Serverless data warehouse for analytics (see Analytics section)

---

## 4. Networking & Content Delivery

### **VPC (Virtual Private Cloud)**
- **Purpose:** Provision private networks, subnets, routes, firewall rules.
- **Features:** Shared VPC, Private Google Access, custom/auto mode

---

### **Cloud Load Balancing**
- **Types:** HTTP(S), SSL Proxy, TCP/UDP, Internal
- **Features:** Global, regional, cross-region, integrates with Cloud Armor (WAF)

---

### **Cloud CDN**
- **Purpose:** Low-latency content delivery at edge locations.

---

### **Cloud Interconnect & VPN**
- **Purpose:** Dedicated private links (Interconnect) or encrypted tunnels (VPN) to GCP.

---

### **Cloud DNS**
- **Purpose:** Scalable, managed DNS service.

---

## 5. Security, Identity & Compliance

### **Cloud IAM**
- **Purpose:** Manage who/what can access GCP resources (users, service accounts, roles)
- **Best Practices:** Least privilege, custom roles, service account separation

---

### **Cloud Identity**
- **Purpose:** Identity management for users/devices across GCP and SaaS

---

### **Cloud Key Management Service (KMS)**
- **Purpose:** Secure key generation, storage, and management

---

### **Cloud Audit Logs**
- **Purpose:** Track all admin/user/data access and API calls

---

### **Security Command Center**
- **Purpose:** Central security visibility and threat detection

---

### **Cloud Armor**
- **Purpose:** DDoS and application firewall protection

---

## 6. Analytics & Machine Learning

### **BigQuery**
- **Purpose:** Serverless, scalable data warehouse for analytics.
- **Features:** Standard SQL, federated queries, ML integration
- **Example (bq):**
    ```sh
    bq query --use_legacy_sql=false 'SELECT COUNT(*) FROM `project.dataset.table`'
    ```

---

### **Dataflow**
- **Purpose:** Serverless stream and batch data processing (Apache Beam)

---

### **Dataproc**
- **Purpose:** Managed Spark/Hadoop clusters

---

### **Pub/Sub**
- **Purpose:** Global messaging for event-driven systems (queues, topics)

---

### **Vertex AI**
- **Purpose:** Unified ML platform for building, training, deploying models

---

### **Looker**
- **Purpose:** Business intelligence, dashboards, data visualization

---

## 7. Developer Tools & Management

### **Cloud Deployment Manager**
- **Purpose:** Infrastructure as code (similar to CloudFormation/ARM templates)
- **Example:**
    ```yaml
    resources:
    - name: my-vm
      type: compute.v1.instance
      properties:
        zone: us-central1-a
        machineType: zones/us-central1-a/machineTypes/e2-medium
        disks:
        - deviceName: boot
          type: PERSISTENT
          boot: true
          autoDelete: true
          initializeParams:
            sourceImage: projects/debian-cloud/global/images/family/debian-11
        networkInterfaces:
        - network: global/networks/default
    ```

---

### **Cloud Logging & Monitoring (Operations Suite)**
- **Purpose:** Metrics, logs, uptime checks, alerts

---

### **Cloud Source Repositories**
- **Purpose:** Private Git hosting

---

### **Cloud Build**
- **Purpose:** CI/CD pipelines

---

### **Cloud Scheduler**
- **Purpose:** Cron jobs as a service

---

## 8. Migration & Hybrid Cloud

### **Migrate for Compute Engine**
- **Purpose:** Migrate VMs from on-premises or other clouds to GCP

---

### **Transfer Appliance**
- **Purpose:** Hardware transfer for large datasets

---

### **Anthos**
- **Purpose:** Manage Kubernetes clusters and workloads across hybrid/multi-cloud

---

## 9. Application Integration

### **Cloud Tasks**
- **Purpose:** Task queues for distributed services

---

### **Workflows**
- **Purpose:** Serverless orchestration for multi-service workflows

---

### **API Gateway**
- **Purpose:** Manage and secure APIs

---

### **Apigee**
- **Purpose:** Full lifecycle API management

---

## 10. Cost Management & Optimization

- **Cloud Billing Reports:** Track and analyze GCP spending
- **Budgets and Alerts:** Set spend limits and notifications
- **Pricing Calculator:** Estimate costs before deploying resources
- **Committed Use Discounts:** Save with long-term commitments

---

## 11. Best Practices and Tips

- Use **labels** for resource management and cost tracking
- Enforce **least privilege** with IAM roles
- Enable **Cloud Audit Logs** and review regularly
- Automate **backups and disaster recovery**
- Monitor with **Cloud Monitoring** and set alerts
- Use **autoscaling** for compute and managed services

---

## 12. Preparing for GCP Certifications

- Build a study plan and get hands-on with Cloud Console & gcloud CLI
- Take Cloudoku’s [practice exams and cheatsheets](https://cloudoku.training/cheatsheets)
- Explore Google Cloud Skills Boost, Qwiklabs, and whitepapers

---

**Good luck on your GCP certification journey!**
