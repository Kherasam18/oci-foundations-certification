# OCI Storage Services

Oracle Cloud Infrastructure (OCI) provides a variety of storage services designed to meet diverse workload requirements, ranging from high-performance databases to unstructured data storage. OCI storage services include **Block Volumes, Local NVMe, File Storage, Object Storage, and Archive Storage**. Each service is optimized for performance, durability, and accessibility.

---

## 1. Understanding Storage Requirements

When selecting a storage service, consider the following factors:

- **Persistence**: Determine whether the storage needs to retain data after instance termination. Persistent storage ensures durability, while non-persistent storage is temporary.  
- **Data Type**: Identify the type of data being stored, such as databases, videos, audio, images, or text files.  
- **Performance**: Evaluate capacity, input/output operations per second (IOPS), and throughput requirements.  
- **Durability**: Understand how many copies of data are maintained to prevent data loss.  
- **Connectivity**: Decide how applications will access the storage, either locally or over the network.  
- **Protocol**: Choose the appropriate interface such as Block, File, or HTTP-based object storage.

---

## 2. Block Storage

Block storage provides **raw storage volumes** that appear to the operating system as a mounted drive. OCI block volumes are highly reliable and are commonly used for compute services.

### Features
- Data is stored in fixed-sized blocks (512 bytes).  
- Supports two types: **Boot Volumes** for OS disks and **Block Volumes** for data disks.  
- Data is replicated across three fault domains for high durability.  
- Automatic backup scheduling is available, eliminating the need for RAID configuration.  

### Use Cases
- Databases such as Oracle DB and MySQL  
- Exchange servers and VMWare workloads  
- Operating system boot disks  

### Block Volume Backups
- Provides a **complete point-in-time snapshot** of a volume.  
- Encrypted and stored in **Object Storage**.  
- Can be restored as a new volume in any availability domain within the same region.  
- Cross-region backups allow disaster recovery across different OCI regions.  

### Block Volume Performance Tiers
- **Basic**: 2 IOPS per GB, 240 KB/s per GB throughput. Best suited for throughput-intensive workloads like large sequential I/O, big data streaming, and data warehouses.  
- **Balanced**: 60 IOPS per GB, 480 KB/s per GB throughput. Ideal for most workloads performing random I/O, such as boot disks.  
- **High Performance**: 75 IOPS per GB, 600 KB/s per GB throughput. Designed for workloads demanding maximum performance, including large databases.  

- Volume sizes range from 50 GB to 32 TB, with up to 32 volumes per instance, allowing a theoretical maximum of one petabyte per instance.

---

## 3. Local NVMe

Local NVMe is **temporary, high-performance storage** directly attached to a compute instance.  

### Key Features
- Extremely fast due to the **Non-Volatile Memory Express (NVMe) interface**.  
- Non-persistent, meaning data is lost if the instance is terminated, but persists across reboots.  
- No RAID, snapshots, or backup capabilities provided by OCI.

### Use Cases
- NoSQL databases  
- In-memory databases  
- Scale-out transactional databases  
- Data warehousing workloads requiring ultra-low latency access  

---

## 4. File Storage

File Storage provides a **hierarchical structure of directories and files**, accessible over the network using standard protocols such as NFS and SMB.  

### Features
- Distributed file systems make remote storage appear local.  
- Supports **NFS version 3**.  
- Data protection includes snapshots, with support for up to 10,000 snapshots per file system.  
- Security includes encryption at rest and in transit.

### Use Cases
- Oracle applications  
- High-performance computing (HPC)  
- Big Data and analytics workloads  
- General-purpose network file systems  

---

## 5. Object Storage

Object Storage treats all data as **objects**, organized in buckets, accessible via HTTP verbs. It is ideal for **unstructured data** and scales to internet-level performance.  

### Features
- Regional service with data replicated across multiple availability domains.  
- Storage classes include **Standard (Hot)** and **Archive (Cold)**.  
- Provides durability, high availability, and cost-effective storage options.

### Use Cases
- Content repositories for images, logs, and videos  
- Backup and archival of large datasets  
- Storing log data for analytics  
- Big Data and Hadoop workloads  

### Object Storage Tiers
- **Standard (Hot) Tier**:  
  - Fast, immediate access for frequently accessed data.  
  - Always serves the most recent copy of data.  
  - Cannot be downgraded to Archive.  

- **Archive (Cold) Tier**:  
  - Designed for rarely accessed data that must be retained long-term.  
  - 10 times cheaper than the Standard tier.  
  - Minimum retention of 90 days.  
  - Objects must be restored before downloading, with a time-to-first-byte of approximately four hours.  
  - Cannot be upgraded to Standard.

---

OCI storage services provide a **robust, scalable, and secure foundation** for applications and data workloads. Selecting the right storage type based on persistence, performance, and access patterns ensures optimal performance and cost efficiency.
