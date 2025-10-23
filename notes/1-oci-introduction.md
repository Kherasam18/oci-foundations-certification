# OCI Introduction

This document provides an overview of **Oracle Cloud Infrastructure (OCI)**, covering core services, architecture, and account/access concepts.

---

## 1. Categories of OCI Services

### Core Infrastructure
- **Compute**: Bare Metal, VM, CPUs, GPUs, HPC
- **Containers**: Containers, Kubernetes (K8s), Container Service
- **OS & VMware**: Linux, Marketplace, OS Management Service
- **Storage**: NVMe, Block, File, Object, Archive, Data Transfer
- **Networking**: VCN, Load Balancer (LB), Service Gateway, FastConnect (FC), VPN, Clusters

### Database Services
- **Oracle DB**: ATP, ADW, JSON, DBCS VM / BM
- **Distributed & OSS**: Heatwave MySQL, Cache, PostgreSQL (PgSQL), OpenSearch

### AI & Data
- **Big Data**: Big Data, Data Flow, Data Integration, Data Catalog, GoldenGate
- **AI Services**: Data Science, Vision, Language, Speech, Document Understanding
- **Generative AI**: Gen AI, Gen AI Agents, Code Assist

### Analytics
- **Business Analytics**: Analytics Cloud, Fusion Analytics

### Application
- **Serverless**: Events, Functions, API Gateway
- **Application Integration**: Integration Cloud, Workflow, Notifications, Email Delivery
- **Business & Industry SaaS**: ERP, HCM, SCM, Sales, Service, Marketing, Vertical Industry Solutions

### Governance & Administration
- **Cloud Ops**: IAM, Compartments, Tagging, Console, Cost Advisor
- **Security**: Cloud Guard, Security Zones, Vault, KMS, Data Safe, DDoS, WAP
- **Observability**: Monitoring, Logging, Logging Analytics, Notifications, Events, Operations Insights, APM, Management Cloud

### Developer Services
- **Low Code**: APEX
- **Application Development**: Visual Builder Studio, GraalVM, Helidon, SQL Developer, Shell, APIs / CLI / SDK / Docs
- **Infrastructure as Code (IaC)**: Resource Manager, Terraform, Ansible

---

## 2. Physical Architecture Concepts

### Regions
- A **region** is a localized geographic area.
- An **availability domain** (AD) is one or more data centers located within a region.
- OCI regions are globally distributed and provide **secure, high-performance, local environments** for businesses to run workloads, meeting regional data regulations.

### Availability Domains
- ADs are **isolated from each other**, fault-tolerant, and very unlikely to fail simultaneously.
- Instances can be distributed across ADs for higher availability.

### Fault Domains
- A **fault domain** is a grouping of hardware and infrastructure within an AD.
- Each AD contains **three fault domains**.
- Fault domains ensure instances are **not on the same physical hardware**, enhancing fault tolerance.
- Data Guard can synchronize data across fault domains and ADs.

### Multi-Cloud & Hybrid Cloud
- OCI has a **partnership with Microsoft Azure**.
- Offers **Dedicated Region Cloud @ Customer** for hybrid cloud solutions.

### Realm
- A **realm** is a logical collection of regions.
- Realms are **isolated** and **do not share data**.

---

## 3. Account & Access Concepts

### Tenancy
- A **tenancy** is a **secure, isolated partition** or account within OCI.

### Compartment
- A **compartment** is a collection of related resources (e.g., instances, VCNs, block volumes).
- Access is restricted to groups with explicit permissions.

### Identity Domains & Policies
- An **identity domain** manages:
  - Users and roles
  - Federating & provisioning users
  - Secure application integration via Oracle Single Sign-On (SSO) and OAuth administration

### Oracle Cloud Identifier (OCID)
- Each OCI resource has a **unique Oracle-assigned ID (OCID)**.
- OCID is visible in both the **Console** and **API**.

### Security Zones
- Security Zones ensure **Compute, Networking, Storage, Database, and other resources** comply with Oracle security principles and best practices.
- A security zone can be associated with **one or more compartments**.

---

