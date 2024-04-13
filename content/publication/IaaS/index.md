---
title: "Introduction to Iaas"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin

# Author notes (optional)
author_notes: ""

date: "2024-04-10"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;t
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: ""

# Summary. An optional shortened abstract.
summary: Beside the the school we have to complete different modules in our company. This publication is about IaaS

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ""
url_code: ""
url_dataset: ""
url_poster: ""
url_project: ""
url_slides: ""
url_source: ""
url_video: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: "Image credit: [**DALL-E**](https://chat.openai.com)"
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---

{{< toc >}}

# IaaS

## Definition

IaaS (Infrastructure as a service) is a cloud computing service model that enables the provision of fundamental IT infrastructure, such as computing power, storage capacity and network resources, via the Internet.

In AWS, various services fall under IaaS. The most important ones are listed below:

- EC2 (Elastic Compute Cloud) + VPC (Virtual Private Cloud)
- S3 (Simple Storage Service)
- Route 53
- RDS (Relational Databas Service)
- EBS (Elastic Block Storage)

## EC2 - What belongs all to that service

### Virtual Machines

Instances with your preferred operating system AMI (based on MacOS, Linux or Windows)

### VPC (Virtual Private Cloud)

Networking in the cloud (including Security Groups, Subnets, Route Tables, Gateways, VPC Peering, VPN, ACL's, etc.)

### Load balancing

Network and Application Load Balancer which can handle traffic distribution between instances. A positive side effect: load balancers also simplify TLS termination and certificate management in combnination with ACM.

### Auto Scaling

Increasing and decreasing of compute-capacity automatically based on traffic volume or behavior.

### Allocation

All the components mentioned above (and more) belong to EC2. But in general, when someone talks about EC2, instances are meant.

## EC2 Instance Lifecycle

An EC2 Instance can have 7 different states:

- 3 are stable
- 4 are transition states which change to stable

  ![EC2 Lifecycle](ec2-lifecycle.jpg "EC2 Instance Lifecycle")

## AMI (Amazon Machine Image)

An AMI is a pre-configured image maintained by AWS for EC2 Instances.

- **Purpose**: Serves as a base configuration for launching new instances.
- **Access Control**: Can be public, explicit (defined access), or implicit (owner only).
- **Source**: Can be self-created, provided by third parties, or AWS.
- **Utility**: Essential for disposable infrastructure, enabling multiple instances with the same setup.
- **Compatibility**: Works seamlessly with Auto-Scaler functionality.
- **Components**: Includes Amazon EBS snapshots or templates for root volumes, launch permissions, and block device mappings for instance launches.

## Metadata & Userdata on an instance

### Metadata

- Technical information about an EC2 instance.
- Includes instance details such as IP address, instance type, security groups, and metrics...

## Userdata

- Custom configuration data for an EC2 instance
  Used to execute scripts, commands, or configuration details upon instance startup, such as installations or configurations

## Instance Types

AWS instances come in various types for specific workload requirements:

- **General Purpose**:

  - Provide a balance of compute, memory, and networking resources.
  - Examples include M-, T-, and Mac1 instances.

- **Compute Optimized**:

  - Ideal for compute-bound applications needing high-performance processors.
  - Examples include C- and HPC instances.

- **Memory Optimized**:

  - Designed for fast performance with large data sets processed in memory.
  - Examples include R-, U-, X-, and Z-instances.

- **Storage Optimized**:

  - Geared towards workloads requiring high, sequential read/write access to large data sets on local storage.
  - Examples include D-, H-, and I-instances.

- **Accelerated Computing**:
  - Utilize hardware accelerators or co-processors for tasks like floating-point calculations, graphics processing, or data pattern matching.
  - Examples include dl-, f-, g-, inf-, p-, and vt-instances.

### Use cases

### General purpose instances

**Web applications**: Optimal for delivering static or dynamic web content and handling user requests.
**Development environments**: Supports code compilation, deployment, testing & use of CI/CD.
M, T instances provide balance between compute, memory & storage.

### Compute Optimized Instances\*\*: Optimized instances

**High Performance Computing (HPC)**: Used in scientific simulations, financial models & engineering (e.g. digitization in mechanical engineering).
**Batch processing**: Ideal for frequently repetitive scenarios such as data analysis & processing with large volumes of data.

HPC instances significantly optimize execution time in contrast to general purpose instances. C instances in turn promote the parallelization of tasks.

### Memory-optimized instances

**Big data analysis**: The large data sets in memory, reduce latency, crucial for analytics.
**In-Memory Databases**: High throughput, low latency for transaction management and query operations. R, X instances increase database performance.

### Memory-optimized instances

**OLTP**: Transaction systems where many transactions take place simultaneously, i.e. concurrently.
**Big Data Processing**: Suitable for Hadoop, data warehousing. D, I instances provide high throughput, IOPS.

### Accelerated compute instances

**Machine learning**: P instances utilize GPUs for efficient algorithm processing, improve training and inference phases.
**Graphics rendering**: Accelerate high-resolution graphics processing & rendering.
