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
  caption: ""
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

Technical information about an EC2 instance. This includes instance details such as IP address, instance type, security groups, and metrics.

### Userdata

Custom configuration data for an EC2 instance. Used to execute scripts, commands, or configuration details upon instance startup, such as installations or configurations

## Instance Types

AWS instances come in various types for specific workload requirements:

**General Purpose**:

- Provide a balance of compute, memory, and networking resources.
- Examples include M-, T-, and Mac1 instances.

**Compute Optimized**:

- Ideal for compute-bound applications needing high-performance processors.
- Examples include C- and HPC instances.

**Memory Optimized**:

- Designed for fast performance with large data sets processed in memory.
- Examples include R-, U-, X-, and Z-instances.

**Storage Optimized**:

- Geared towards workloads requiring high, sequential read/write access to large data sets on local storage.
- Examples include D-, H-, and I-instances.

**Accelerated Computing**:

- Utilize hardware accelerators or co-processors for tasks like floating-point calculations, graphics processing, or data pattern matching.
- Examples include dl-, f-, g-, inf-, p-, and vt-instances.

### Task: Use cases

#### General purpose instances

**Web applications**: Optimal for delivering static or dynamic web content and handling user requests.

**Development environments**: Supports code compilation, deployment, testing & use of CI/CD.
M, T instances provide balance between compute, memory & storage.

#### Compute Optimized Instances

**High Performance Computing (HPC)**: Used in scientific simulations, financial models & engineering (e.g. digitization in mechanical engineering).

**Batch processing**: Ideal for frequently repetitive scenarios such as data analysis & processing with large volumes of data.

HPC instances significantly optimize execution time in contrast to general purpose instances. C instances in turn promote the parallelization of tasks.

#### Memory-optimized instances

**Big data analysis**: The large data sets in memory, reduce latency, crucial for analytics.

**In-Memory Databases**: High throughput, low latency for transaction management and query operations. R, X instances increase database performance.

#### Memory-optimized instances

**OLTP**: Transaction systems where many transactions take place simultaneously, i.e. concurrently.

**Big Data Processing**: Suitable for Hadoop, data warehousing. D, I instances provide high throughput, IOPS.

#### Accelerated compute instances

**Machine learning**: P instances utilize GPUs for efficient algorithm processing, improve training and inference phases.

**Graphics rendering**: Accelerate high-resolution graphics processing & rendering.

## AWS EC2 Instance Pricing Models

### On-Demand Instances

- Pay by hour or second, depending on the instance type (Most expensive EC2 pricing model).
- Best for applications with short-term, spiky, or unpredictable workloads that cannot be interrupted.
- No long-term commitment or upfront payment required.

#### Task: On-Demand Instances: Dynamic Auto-Scaling During Sales Events

Imagine managing an e-commerce platform's web servers in EC2 during Black Friday or Cyber Week. On-demand instances would be perfect, as you don't have to make a long-term commitment and therefore have the ability to scale flexibly at any time.

### Reserved Instances

- Significant discount over On-Demand rates, in exchange for a commitment to use the instance for a 1 or 3-year term (Less expensive EC2 pricing model).
- Ideal for applications with steady state or predictable usage.
- Upfront payment and long-term commitment (1 or 3 years) required.

#### Task: Reserved Instances: Backend for Financial Transactions

Imagine you manage a bank's back-end infrastructure for financial transactions in EC2. The servers must be stable and run for several years. The reserved instances would be available to the bank at a cheaper and more predictable hourly rate due to the long-term commitment and are constantly available.

### Spot Instances

- Purchase unused EC2 capacity at significantly lower rates than On-Demand (Cheapest EC2 pricing model).
- Suitable for fault-tolerant applications such as big data, containerized workloads, and CI/CD pipelines that can tolerate interruptions.
- No long-term commitment: price is based on supply & demand + instances can be interrupted within a short time when EC2 reclaims capacity.

#### Task: Spot Instances: Overnight Batch Processing

Imagine you want to batch process the inventory of your ecommerse website as cheaply as possible and at off-peak times on your backend. Using spot instances would be optimal as it minimizes costs by using unused EC2 capacity during off-peak hours to make important updates based on daily sales and inventory changes.

## AWS Regions & Availability Zones (AZ)

### Regions

- **Definition:** Geographic areas like different countries, each region consists of a network of several Availability Zones.
- **Variability:** The software and services available can differ from one region to another.

### Availability Zones (AZ)

- **Relation to Regions:** Each AZ belongs to a region but is geographically distant enough (approximately 100 km apart) to ensure that ideally only one AZ is affected in the event of a disaster.
- **Consistency:** Within the same region, different AZs generally offer the same software and services.

### Availability of AZs

By utilizing more than one Availability Zone, you can guarantee higher availability. In case one AZ fails, others can provide a backup.

![Regions & AZs](region-az.png "Regions & AZs")

## EC2 Fleet

EC2 Fleets makes it possible to launch multiple ec2 instances with different pricing models (on-demand, reserved & spot) across multiple availability zones.

### Task: Use-Cases Batch Processing

EC2 allows the configuration of fleets using a combination of Spot Instances and On-Demand Instances. For batch processing tasks that are not time-sensitive and primarily run overnight, Spot Instances can be utilized to minimize costs. The fleet can be set to use Spot Instances until a predefined price cap is reached. If Spot prices rise above this cap, EC2 Fleet automatically supplements the fleet with On-Demand Instances to ensure continuous processing without manual intervention.

## Elastic Network Interface (ENI)

An Elastic Network Interface (ENI) is a virtual network card used to attach to instances in Amazon Web Services (AWS) within a Virtual Private Cloud (VPC).

When an instance is launched within a VPC, or more specifically within a subnet of a VPC, an ENI is automatically attached to it. For example, if you launch an EC2 instance in a VPC subnet, the instance will have an ENI with a primary private IPv4 address assigned from the subnet’s IP range. Additional secondary private IPv4 addresses can be attached to the same ENI. Instances can have multiple ENIs attached, known as primary and secondary ENIs, which can be used for network and security management tasks within the VPC. Each ENI can also be assigned an Elastic IP address, and supports source/destination checking, which controls whether it can route network traffic.

## VPC Overview

A Virtual Private Cloud (VPC) is a virtual network designed to provide the same level of functionality as a traditional network. It operates as an isolated environment within an AWS account.
A VPC allows subnetting, allocation of IP ranges, and spans across all Availability Zones (AZs) within a single region. Each subnet in a VPC is belonging to one AZ.

### Default and Nondefault VPCs

Each region provides a default VPC, which is free of charge (Account creation after 12/04/2013). This VPC includes a default subnet in each AZ and supports all the functionality of EC2-VPC. EC2 Instances with no VPC specifications get launched into the default VPC.

Users have also the possibility to create their own VPCs, known as nondefault VPCs, to meet specific network configurations. Any subnets created within a nondefault VPC or added to the default VPC are referred to as nondefault subnets.

![VPC](vpc.png "VPC")

## Subnets and Route Tables in VPC

### Subnets

Subnets are subdivisions of a VPC and are used to segment and manage network traffic within different portions of a VPC. Each subnet is associated with a specific Availability Zone and can have its security and routing policies.

#### Public Subnet

A public subnet in AWS allows instances to access and be accessed from the internet. This is enabled by a route in its route table pointing to an Internet Gateway (IGW). Instances in public subnets typically have public IP addresses.

#### Private Subnet

A private subnet does not have a route to an IGW and therefore cannot directly access the internet. It is designed for internal-only traffic and uses for example a NAT Gateway for internet access, which restricts incoming connections.

![Private & public subnets](subnets.png "Subnets")

### Route Tables

Route tables within a VPC define the paths for network traffic. Each subnet must be associated with a route table, which determines where network traffic is directed. Route tables control the routing between subnets, for example to the internet via an Internet Gateway, and to other AWS services.

Route tables can be customized to direct traffic based on the origin and destination. This includes routes for local networking within the VPC and routes that allow subnets to communicate with external networks.

## Gateways for VPC

### Internet Gateway

An Internet Gateway enables communication between instances in a VPC and the internet. It supports both inbound and outbound traffic but only connects with public subnets.

#### Configuration

For a subnet to communicate through the Internet Gateway, its routing table must contain an entry for this gateway. Subnets without an entry for the Internet Gateway in their routing table, typically private subnets, do not have direct internet access through this gateway.

#### Communication Requirements

Instances in public subnets can communicate with the internet if they meet specific conditions: they must either have a public IPv4 address or an Elastic IP address associated with a private IPv4 address.

### NAT Gateway

A Network Address Translation (NAT) Gateway allows instances in private subnets to access the internet, AWS services, and private data centers, supporting only outbound (egress) traffic.

#### Public NAT Gateway

A Public NAT Gateway is deployed in a public subnet, using an Elastic IP address for internet communication. It enables instances in private subnets to initiate outbound connections to the internet while preventing inbound traffic.

#### Private NAT Gateway

A Private NAT Gateway, while less common, refers to a configuration where NAT services are restricted within private network environments, such as between different private subnets within the same VPC. This setup is typically used to control and isolate internal network traffic without exposure to external networks.

![IGW & NAT-GW](subnets.png "IGW & NAT-GW")

### Transit Gateways and Usage

AWS Transit Gateway acts as a network hub that simplifies connectivity between VPCs, AWS Direct Connect, and VPN connections. It centralizes the management of interconnectivity and routing policies, reducing the complexity of managing multiple network connections.

- **Centralized Hub:** Simplifies the network architecture by acting as a central point to manage routing and connections across multiple VPCs and external connections.
- **Scalable Connectivity:** Supports thousands of VPC and VPN connections within one transit gateway.
- **Routing Control:** Provides flexible routing options, including dynamic and static routes.

### Centralized Router

- **Usage:** Configure your transit gateway as a centralized router that connects all of your VPCs, AWS Direct Connect, and AWS Site-to-Site VPN connections.

### Isolated VPCs

- **Usage:** Configure your transit gateway to function as multiple isolated routers (not limited to one routetable; one rt per connection). This is the same as using multiple transit gateways but offers more flexibility in scenarios where routes and attachments might change.

### Isolated VPCs with Shared Services

- **Usage:** Set up your transit gateway as multiple isolated routers that utilize a shared service. Similar to the isolated VPCs scenario, this provides additional flexibility in cases where routes and attachments are subject to modification.

![Transit Gateway](transit-gateway.png "AWS Transit Gateway")

### Direct Connect Gateway

AWS Direct Connect provides a dedicated network connection from an on-premise network to AWS. Unlike internet-based VPNs, Direct Connect offers a private, consistent, and low-latency connection that bypasses the public internet. This service is particularly advantageous for applications requiring stable, high-throughput, or real-time network performance.

- **Dedicated Connection:** Provides a physical connection between the customer’s network and AWS, ensuring consistent network performance.
- **Reduced Bandwidth Costs:** Potentially lowers network costs by reducing bandwidth charges typically associated with high-volume data transfers over the internet.
- **Compatibility with AWS Services:** Integrates with other AWS services, such as Amazon VPC, AWS Transit Gateway, and AWS VPN solutions.

![Direct Connect](direct-connect-tgw.png "AWS Direct Connect")

### VPC Peering

VPC Peering allows direct network connectivity between different VPCs, facilitating bidirectional traffic flow from any subnet within the VPCs involved. This connection is used exclusively for internal AWS traffic. You could for example peer your default VPC within a region with the underlying VPC of your AWS Lightsail infrastructure. This allows you to connect other AWS services (outside of Lighsail) with your Lightsail components.

![VPC Peering](vpc-peering.png "VPC Peering")

## Possible VPN Options in AWS

### AWS Site-to-Site VPN

AWS Site-to-Site VPN establishes secure IPsec connections between an on-premise network and AWS VPCs. This service encrypts data transmitted over the internet, ensuring secure communication between corporate data centers and the AWS cloud. It supports static and dynamic routing options, suitable for extending data centers or for disaster recovery setups.

![AWS Site-to-Site VPN](site-to-site.png "AWS Site-to-Site VPN")

### AWS Client VPN

AWS Client VPN is a managed client-based VPN service that allows secure access to AWS networks and on-premise environments from any location. Supporting OpenVPN clients, it enables seamless connectivity across various platforms, ensuring end-to-end encryption and fine-grained access control through integration with AWS Identity and Access Management (IAM).

![AWS Client VPN](client-vpn.png "AWS Client VPN")

### AWS VPN CloudHub

Designed for organizations with multiple branch offices, AWS VPN CloudHub uses a hub-and-spoke model to connect each branch to AWS via a virtual private gateway. This setup supports secure communication across the branches, leveraging the AWS network backbone for optimized and encrypted data flow.

![AWS VPN CloudHub](vpn-cloudhub.png "AWS VPN CloudHub")

## VPC Peering Task

### Task

Duplicate your existing VPC from the task before, including all subnets and instances, but without adding any gateways. Establish a VPC peering connection between the original and the new VPC.

**Steps**:

- Create a copy of the original VPC along with its private and public subnets and instances. Ensure the new VPC does not include any gateways.
- Connect both VPCs (VPC1 and VPC2) via VPC peering:

#### Components

The basic infrastructure includes two Virtual Private Clouds (VPCs) that are peered together.

**Original VPC**

- **Subnets**: Includes one private and one public subnet with one route table each.
- **Internet Gateway (IGW)**: Connected to the public subnet to allow outbound internet access.
- **NAT Gateway (NAT-G)**: Placed within the public subnet; it provides internet access to instances in the private subnet.
- **Security Groups**: Configured for both public and private instances to allow SSH and ICMP protocols.
- **EC2 Instances**: Ubuntu instances deployed in both the public and private subnets.

**Duplicate VPC**

- **Subnets**: Includes one private and one public subnet.
- **Security Groups**: Similar setup as the original VPC, allowing SSH and ICMP.
- **EC2 Instances**: Ubuntu instances located in both the public and private subnets.
- **Gateways**: None are present as specified.

![Base Infrastructure](vpc-peering-base.png "Base Infrastructure")

- Test Connectivity between VPCs
  - Ping from VPC1 public subnet to VPC2 public subnet.
  - Ping from VPC1 public subnet to VPC2 private subnet.
  - Ping from VPC1 private subnet to VPC2 public subnet.
  - Ping from VPC1 private subnet to VPC2 private subnet.
  - Repeat tests from VPC2 to VPC1.
- Record observations and modify settings to enable all eight possible connections:
  **Erkenntnisse**:

1. Mit der aktuellen Konfiguration ist es nicht möglich zwischen den beiden VPCs zu kommunizieren. Dementsprechend habe ich auch keinen SSH-Access zu den public und private Instanzen in VPC2.
2. Innerhalb VPC1 zwischen Private und Public Subnet ist die Kommunikation möglich.

- Ensure VPC2 does not access the internet directly. Configure VPC2 (both subnets) to access the internet through VPC1's public subnet.
