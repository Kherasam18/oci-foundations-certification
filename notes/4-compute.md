# OCI Compute Services

Oracle Cloud Infrastructure (OCI) provides a variety of compute services that allow you to run applications, containers, and workloads with high performance, scalability, and flexibility. Compute services in OCI include Bare Metal servers, Virtual Machines, Dedicated Virtual Hosts, the Container Engine for Kubernetes, and Functions.

---

## 1. Bare Metal Instances

Bare Metal instances provide **direct access to physical hardware** without any virtualization. This allows maximum performance and control for workloads that require it.  

### Key Features
- Runs your **code, application containers, language runtime, and operating system** directly on the hardware.  
- Single-tenant environment, ensuring no other customers share the server.  

### Use Cases
- Performance-intensive workloads, such as databases.  
- Applications that require **specific hypervisors**.  
- Workloads that require **bring-your-own licensing**, for example, Microsoft SQL Server or Exchange.  
- Workloads that cannot be virtualized.

---

## 2. Virtual Machines (VMs)

Virtual Machines are **multi-tenant instances** hosted on physical servers with hypervisor-based virtualization.  

### Key Features
- Run code, application containers, language runtime, and operating system as a guest on a host server.  
- Supports Intel and AMD processors, with GPU and HPC options for specialized workloads.  
- Placed on a virtual network with powerful connectivity options.  
- Depends on other OCI services such as Block Volume for boot or data storage and Virtual Cloud Network (VCN) for networking.

### Use Cases
- Deploy legacy applications running on Windows or Linux.  
- Migrate applications from on-premises to OCI.  
- Control all aspects of the environment while leveraging virtualization.

---

## 3. Dedicated Virtual Hosts

Dedicated Virtual Hosts provide **single-tenant VM environments**. This gives you isolation similar to Bare Metal instances but allows multiple VMs on the same hardware.  

### Use Cases
- Organizations needing **single-tenant security**.  
- Running multiple VMs for applications while maintaining physical isolation from other tenants.

---

## 4. Instance Basics

OCI instances are configurable in terms of **CPU, RAM, and bandwidth**. Key considerations include:  

- Instance shapes support **both vertical and horizontal scaling**.  
- You can choose instances with GPUs or HPC capabilities with RDMA support for high-performance workloads.  
- Instances are deployed on virtual networks with flexible connectivity options.  
- Instances integrate with **Block Volume** for storage and **VCN** for networking.

---

## 5. Scaling

### Vertical Scaling
- Increase or decrease the resources of a single instance.  
- Requires downtime during resizing.  

### Autoscaling
- Automatically adjusts the number of VM instances in response to workload demands.  
- Enables **high availability**, as if one instance fails, others continue serving traffic.  
- Uses **instance configurations** derived from a gold image, which includes OS, metadata, instance shape, VNICs, storage, and subnets.  
- Instances are organized into **instance pools**, which can be deployed across multiple availability domains.  
- **Scaling rules** define when to scale out or scale in based on metrics like CPU usage or memory consumption.

---

## 6. Container Deployment

Containers can be deployed in multiple ways:  

1. Manually SSH into instances and run Docker.  
2. Use scripting or configuration management tools for automation.  
3. Use **orchestration systems**, such as Kubernetes, for automated deployment and scaling.

### Oracle Kubernetes Engine (OKE)
- Fully managed Kubernetes service in OCI.  
- Containers run in **pods**, which are placed on nodes (instances).  
- Supports integration with **OCI Registry (OCIR)** for storing container images.  
- Ideal for deploying microservices and cloud-native applications.

---

## 7. Functions

OCI Functions allows running **small, event-driven blocks of code**.  

### Key Features
- Typically perform a **single, focused task**.  
- Functions are stored as Docker images and invoked only when triggered.  
- Supports triggers via CLI commands or signed HTTP requests.  
- Pay only for the execution time of the function, making it **cost-efficient**.

### Deployment Flow
1. Push the container image to **OCI Registry**.  
2. Configure the function trigger.  
3. Code runs only when triggered by the event.  
4. Automatically scales to handle workload as needed.

---

OCI Compute Services provide the **flexibility, scalability, and performance** required for a wide range of workloads, from high-performance databases and legacy applications to modern cloud-native microservices and event-driven functions.
