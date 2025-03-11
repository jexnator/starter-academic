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

# {{< highlight go >}}<b>IaaS</b>{{< /highlight >}}<br>

## {{< highlight go >}}<b>Definition</b>{{< /highlight >}}<br>

IaaS (Infrastructure as a service) is a cloud computing service model that enables the provision of fundamental IT infrastructure, such as computing power, storage capacity and network resources, via the Internet.

In AWS, various services fall under IaaS. The most important ones are listed below:

- EC2 (Elastic Compute Cloud) + VPC (Virtual Private Cloud)
- S3 (Simple Storage Service)
- Route 53
- RDS (Relational Databas Service)
- EBS (Elastic Block Storage)

## {{< highlight go >}}<b>EC2 - What belongs all to that service</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Virtual Machines</b>{{< /highlight >}}<br>

Instances with your preferred operating system AMI (based on MacOS, Linux or Windows)

### {{< highlight go >}}<b>VPC (Virtual Private Cloud)</b>{{< /highlight >}}<br>

Networking in the cloud (including Security Groups, Subnets, Route Tables, Gateways, VPC Peering, VPN, ACL's, etc.)

### {{< highlight go >}}<b>Load balancing</b>{{< /highlight >}}<br>

Network and Application Load Balancer which can handle traffic distribution between instances. A positive side effect: load balancers also simplify TLS termination and certificate management in combnination with ACM.

### {{< highlight go >}}<b>Auto Scaling</b>{{< /highlight >}}<br>

Increasing and decreasing of compute-capacity automatically based on traffic volume or behavior.

### {{< highlight go >}}<b>Allocation</b>{{< /highlight >}}<br>

All the components mentioned above (and more) belong to EC2. But in general, when someone talks about EC2, instances are meant.

## {{< highlight go >}}<b>EC2 Instance Lifecycle</b>{{< /highlight >}}<br>

An EC2 Instance can have 7 different states:

- 3 are stable
- 4 are transition states which change to stable

  ![EC2 Lifecycle](ec2-lifecycle.jpg "EC2 Instance Lifecycle")

## {{< highlight go >}}<b>AMI (Amazon Machine Image)</b>{{< /highlight >}}<br>

An AMI is a pre-configured image maintained by AWS for EC2 Instances.

- **Purpose**: Serves as a base configuration for launching new instances.
- **Access Control**: Can be public, explicit (defined access), or implicit (owner only).
- **Source**: Can be self-created, provided by third parties, or AWS.
- **Utility**: Essential for disposable infrastructure, enabling multiple instances with the same setup.
- **Compatibility**: Works seamlessly with Auto-Scaler functionality.
- **Components**: Includes Amazon EBS snapshots or templates for root volumes, launch permissions, and block device mappings for instance launches.

## {{< highlight go >}}<b>Metadata & Userdata on an instance</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Metadata</b>{{< /highlight >}}<br>

Technical information about an EC2 instance. This includes instance details such as IP address, instance type, security groups, and metrics.

### {{< highlight go >}}<b>Userdata</b>{{< /highlight >}}<br>

Custom configuration data for an EC2 instance. Used to execute scripts, commands, or configuration details upon instance startup, such as installations or configurations

## {{< highlight go >}}<b>Instance Types</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Task: Use cases</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>General purpose instances</b>{{< /highlight >}}<br>

**Web applications**: Optimal for delivering static or dynamic web content and handling user requests.

**Development environments**: Supports code compilation, deployment, testing & use of CI/CD.
M, T instances provide balance between compute, memory & storage.

#### {{< highlight go >}}<b>Compute Optimized Instances</b>{{< /highlight >}}<br>

**High Performance Computing (HPC)**: Used in scientific simulations, financial models & engineering (e.g. digitization in mechanical engineering).

**Batch processing**: Ideal for frequently repetitive scenarios such as data analysis & processing with large volumes of data.

HPC instances significantly optimize execution time in contrast to general purpose instances. C instances in turn promote the parallelization of tasks.

#### {{< highlight go >}}<b>Memory-optimized instances</b>{{< /highlight >}}<br>

**Big data analysis**: The large data sets in memory, reduce latency, crucial for analytics.

**In-Memory Databases**: High throughput, low latency for transaction management and query operations. R, X instances increase database performance.

#### {{< highlight go >}}<b>Memory-optimized instances</b>{{< /highlight >}}<br>

**OLTP**: Transaction systems where many transactions take place simultaneously, i.e. concurrently.

**Big Data Processing**: Suitable for Hadoop, data warehousing. D, I instances provide high throughput, IOPS.

#### {{< highlight go >}}<b>Accelerated compute instances</b>{{< /highlight >}}<br>

**Machine learning**: P instances utilize GPUs for efficient algorithm processing, improve training and inference phases.

**Graphics rendering**: Accelerate high-resolution graphics processing & rendering.

## {{< highlight go >}}<b>AWS EC2 Instance Pricing Models</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>On-Demand Instances</b>{{< /highlight >}}<br>

- Pay by hour or second, depending on the instance type (Most expensive EC2 pricing model).
- Best for applications with short-term, spiky, or unpredictable workloads that cannot be interrupted.
- No long-term commitment or upfront payment required.

#### {{< highlight go >}}<b>Task: On-Demand Instances: Dynamic Auto-Scaling During Sales Events</b>{{< /highlight >}}<br>

Imagine managing an e-commerce platform's web servers in EC2 during Black Friday or Cyber Week. On-demand instances would be perfect, as you don't have to make a long-term commitment and therefore have the ability to scale flexibly at any time.

### {{< highlight go >}}<b>Reserved Instances</b>{{< /highlight >}}<br>

- Significant discount over On-Demand rates, in exchange for a commitment to use the instance for a 1 or 3-year term (Less expensive EC2 pricing model).
- Ideal for applications with steady state or predictable usage.
- Upfront payment and long-term commitment (1 or 3 years) required.

#### {{< highlight go >}}<b>Task: Reserved Instances: Backend for Financial Transactions</b>{{< /highlight >}}<br>

Imagine you manage a bank's back-end infrastructure for financial transactions in EC2. The servers must be stable and run for several years. The reserved instances would be available to the bank at a cheaper and more predictable hourly rate due to the long-term commitment and are constantly available.

### {{< highlight go >}}<b>Spot Instances</b>{{< /highlight >}}<br>

- Purchase unused EC2 capacity at significantly lower rates than On-Demand (Cheapest EC2 pricing model).
- Suitable for fault-tolerant applications such as big data, containerized workloads, and CI/CD pipelines that can tolerate interruptions.
- No long-term commitment: price is based on supply & demand + instances can be interrupted within a short time when EC2 reclaims capacity.

#### {{< highlight go >}}<b>Task: Spot Instances: Overnight Batch Processing</b>{{< /highlight >}}<br>

Imagine you want to batch process the inventory of your ecommerse website as cheaply as possible and at off-peak times on your backend. Using spot instances would be optimal as it minimizes costs by using unused EC2 capacity during off-peak hours to make important updates based on daily sales and inventory changes.

## {{< highlight go >}}<b>AWS Regions & Availability Zones (AZ)</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Regions</b>{{< /highlight >}}<br>

- **Definition:** Geographic areas like different countries, each region consists of a network of several Availability Zones.
- **Variability:** The software and services available can differ from one region to another.

### {{< highlight go >}}<b>Availability Zones (AZ)</b>{{< /highlight >}}<br>

- **Relation to Regions:** Each AZ belongs to a region but is geographically distant enough (approximately 100 km apart) to ensure that ideally only one AZ is affected in the event of a disaster.
- **Consistency:** Within the same region, different AZs generally offer the same software and services.

### {{< highlight go >}}<b>Availability of AZs</b>{{< /highlight >}}<br>

By utilizing more than one Availability Zone, you can guarantee higher availability. In case one AZ fails, others can provide a backup.

![Regions & AZs](region-az.png "Regions & AZs")

## {{< highlight go >}}<b>EC2 Fleet</b>{{< /highlight >}}<br>

EC2 Fleets makes it possible to launch multiple ec2 instances with different pricing models (on-demand, reserved & spot) across multiple availability zones.

### {{< highlight go >}}<b>Task: Use-Cases Batch Processing</b>{{< /highlight >}}<br>

EC2 allows the configuration of fleets using a combination of Spot Instances and On-Demand Instances. For batch processing tasks that are not time-sensitive and primarily run overnight, Spot Instances can be utilized to minimize costs. The fleet can be set to use Spot Instances until a predefined price cap is reached. If Spot prices rise above this cap, EC2 Fleet automatically supplements the fleet with On-Demand Instances to ensure continuous processing without manual intervention.

## {{< highlight go >}}<b>Elastic Network Interface (ENI)</b>{{< /highlight >}}<br>

An Elastic Network Interface (ENI) is a virtual network card used to attach to instances in Amazon Web Services (AWS) within a Virtual Private Cloud (VPC).

When an instance is launched within a VPC, or more specifically within a subnet of a VPC, an ENI is automatically attached to it. For example, if you launch an EC2 instance in a VPC subnet, the instance will have an ENI with a primary private IPv4 address assigned from the subnet’s IP range. Additional secondary private IPv4 addresses can be attached to the same ENI. Instances can have multiple ENIs attached, known as primary and secondary ENIs, which can be used for network and security management tasks within the VPC. Each ENI can also be assigned an Elastic IP address, and supports source/destination checking, which controls whether it can route network traffic.

## {{< highlight go >}}<b>VPC Overview</b>{{< /highlight >}}<br>

A Virtual Private Cloud (VPC) is a virtual network designed to provide the same level of functionality as a traditional network. It operates as an isolated environment within an AWS account.
A VPC allows subnetting, allocation of IP ranges, and spans across all Availability Zones (AZs) within a single region. Each subnet in a VPC is belonging to one AZ.

### {{< highlight go >}}<b>Default and Nondefault VPCs</b>{{< /highlight >}}<br>

Each region provides a default VPC, which is free of charge (Account creation after 12/04/2013). This VPC includes a default subnet in each AZ and supports all the functionality of EC2-VPC. EC2 Instances with no VPC specifications get launched into the default VPC.

Users have also the possibility to create their own VPCs, known as nondefault VPCs, to meet specific network configurations. Any subnets created within a nondefault VPC or added to the default VPC are referred to as nondefault subnets.

![VPC](vpc.png "VPC")

## {{< highlight go >}}<b>Subnets and Route Tables in VPC</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Subnets</b>{{< /highlight >}}<br>

Subnets are subdivisions of a VPC and are used to segment and manage network traffic within different portions of a VPC. Each subnet is associated with a specific Availability Zone and can have its security and routing policies.

#### {{< highlight go >}}<b>Public Subnet</b>{{< /highlight >}}<br>

A public subnet in AWS allows instances to access and be accessed from the internet. This is enabled by a route in its route table pointing to an Internet Gateway (IGW). Instances in public subnets typically have public IP addresses.

#### {{< highlight go >}}<b>Private Subnet</b>{{< /highlight >}}<br>

A private subnet does not have a route to an IGW and therefore cannot directly access the internet. It is designed for internal-only traffic and uses for example a NAT Gateway for internet access, which restricts incoming connections.

![Private & public subnets](subnets.png "Subnets")

### {{< highlight go >}}<b>Route Tables</b>{{< /highlight >}}<br>

Route tables within a VPC define the paths for network traffic. Each subnet must be associated with a route table, which determines where network traffic is directed. Route tables control the routing between subnets, for example to the internet via an Internet Gateway, and to other AWS services.

Route tables can be customized to direct traffic based on the origin and destination. This includes routes for local networking within the VPC and routes that allow subnets to communicate with external networks.

## {{< highlight go >}}<b>Gateways for VPC</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Internet Gateway</b>{{< /highlight >}}<br>

An Internet Gateway enables communication between instances in a VPC and the internet. It supports both inbound and outbound traffic but only connects with public subnets.

#### {{< highlight go >}}<b>Configuration</b>{{< /highlight >}}<br>

For a subnet to communicate through the Internet Gateway, its routing table must contain an entry for this gateway. Subnets without an entry for the Internet Gateway in their routing table, typically private subnets, do not have direct internet access through this gateway.

#### {{< highlight go >}}<b>Communication Requirements</b>{{< /highlight >}}<br>

Instances in public subnets can communicate with the internet if they meet specific conditions: they must either have a public IPv4 address or an Elastic IP address associated with a private IPv4 address.

### {{< highlight go >}}<b>NAT Gateway</b>{{< /highlight >}}<br>

A Network Address Translation (NAT) Gateway allows instances in private subnets to access the internet, AWS services, and private data centers, supporting only outbound (egress) traffic.

#### {{< highlight go >}}<b>Public NAT Gateway</b>{{< /highlight >}}<br>

A Public NAT Gateway is deployed in a public subnet, using an Elastic IP address for internet communication. It enables instances in private subnets to initiate outbound connections to the internet while preventing inbound traffic.

#### {{< highlight go >}}<b>Private NAT Gateway</b>{{< /highlight >}}<br>

A Private NAT Gateway, while less common, refers to a configuration where NAT services are restricted within private network environments, such as between different private subnets within the same VPC. This setup is typically used to control and isolate internal network traffic without exposure to external networks.

![IGW & NAT-GW](subnets.png "IGW & NAT-GW")

### {{< highlight go >}}<b>Transit Gateways and Usage</b>{{< /highlight >}}<br>

AWS Transit Gateway acts as a network hub that simplifies connectivity between VPCs, AWS Direct Connect, and VPN connections. It centralizes the management of interconnectivity and routing policies, reducing the complexity of managing multiple network connections.

- **Centralized Hub:** Simplifies the network architecture by acting as a central point to manage routing and connections across multiple VPCs and external connections.
- **Scalable Connectivity:** Supports thousands of VPC and VPN connections within one transit gateway.
- **Routing Control:** Provides flexible routing options, including dynamic and static routes.

### {{< highlight go >}}<b>Centralized Router</b>{{< /highlight >}}<br>

- **Usage:** Configure your transit gateway as a centralized router that connects all of your VPCs, AWS Direct Connect, and AWS Site-to-Site VPN connections.

### {{< highlight go >}}<b>Isolated VPCs</b>{{< /highlight >}}<br>

- **Usage:** Configure your transit gateway to function as multiple isolated routers (not limited to one routetable; one rt per connection). This is the same as using multiple transit gateways but offers more flexibility in scenarios where routes and attachments might change.

### {{< highlight go >}}<b>Isolated VPCs with Shared Services</b>{{< /highlight >}}<br>

- **Usage:** Set up your transit gateway as multiple isolated routers that utilize a shared service. Similar to the isolated VPCs scenario, this provides additional flexibility in cases where routes and attachments are subject to modification.

![Transit Gateway](transit-gateway.png "AWS Transit Gateway")

### {{< highlight go >}}<b>Direct Connect Gateway</b>{{< /highlight >}}<br>

AWS Direct Connect provides a dedicated network connection from an on-premise network to AWS. Unlike internet-based VPNs, Direct Connect offers a private, consistent, and low-latency connection that bypasses the public internet. This service is particularly advantageous for applications requiring stable, high-throughput, or real-time network performance.

- **Dedicated Connection:** Provides a physical connection between the customer’s network and AWS, ensuring consistent network performance.
- **Reduced Bandwidth Costs:** Potentially lowers network costs by reducing bandwidth charges typically associated with high-volume data transfers over the internet.
- **Compatibility with AWS Services:** Integrates with other AWS services, such as Amazon VPC, AWS Transit Gateway, and AWS VPN solutions.

![Direct Connect](direct-connect-tgw.png "AWS Direct Connect")

### {{< highlight go >}}<b>VPC Peering</b>{{< /highlight >}}<br>

VPC Peering allows direct network connectivity between different VPCs, facilitating bidirectional traffic flow from any subnet within the VPCs involved. This connection is used exclusively for internal AWS traffic. You could for example peer your default VPC within a region with the underlying VPC of your AWS Lightsail infrastructure. This allows you to connect other AWS services (outside of Lighsail) with your Lightsail components.

![VPC Peering](vpc-peering.png "VPC Peering")

## {{< highlight go >}}<b>Possible VPN Options in AWS</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>AWS Site-to-Site VPN</b>{{< /highlight >}}<br>

AWS Site-to-Site VPN establishes secure IPsec connections between an on-premise network and AWS VPCs. This service encrypts data transmitted over the internet, ensuring secure communication between corporate data centers and the AWS cloud. It supports static and dynamic routing options, suitable for extending data centers or for disaster recovery setups.

![AWS Site-to-Site VPN](site-to-site.png "AWS Site-to-Site VPN")

### {{< highlight go >}}<b>AWS Client VPN</b>{{< /highlight >}}<br>

AWS Client VPN is a managed client-based VPN service that allows secure access to AWS networks and on-premise environments from any location. Supporting OpenVPN clients, it enables seamless connectivity across various platforms, ensuring end-to-end encryption and fine-grained access control through integration with AWS Identity and Access Management (IAM).

![AWS Client VPN](client-vpn.png "AWS Client VPN")

### {{< highlight go >}}<b>AWS VPN CloudHub</b>{{< /highlight >}}<br>

Designed for organizations with multiple branch offices, AWS VPN CloudHub uses a hub-and-spoke model to connect each branch to AWS via a virtual private gateway. This setup supports secure communication across the branches, leveraging the AWS network backbone for optimized and encrypted data flow.

![AWS VPN CloudHub](vpn-cloudhub.png "AWS VPN CloudHub")

## {{< highlight go >}}<b>VPC Peering Task</b>{{< /highlight >}}<br>

> Duplicate your existing VPC from the task before, including all subnets and instances, but without adding any gateways. Establish a VPC peering connection between the original and the new VPC.

> **Steps**:
>
> 1.  Create a copy of the original VPC along with its private and public subnets and instances. Ensure the new VPC does not include any gateways.
> 2.  Connect both VPCs (VPC1 and VPC2) via VPC peering.

The basic infrastructure includes two Virtual Private Clouds (VPCs) that are peered together.
**Original VPC**

- **Subnets**: Includes one private and one public subnet with one route table each.
- **Internet Gateway (IGW)**: Connected to the public subnet to allow in- & egress traffic to the internet.
- **NAT Gateway (NAT-G)**: Placed within the public subnet; it provides egress internet access to instances in the private subnet.
- **Security Groups**: Configured for both public and private instances to allow SSH and ICMP.
- **EC2 Instances**: Ubuntu instances deployed in both the public and private subnets.

**Duplicate VPC**

- **Subnets**: Includes one private and one public subnet.
- **Security Groups**: Similar setup as the original VPC, allowing SSH and ICMP.
- **EC2 Instances**: Ubuntu instances located in both the public and private subnets.
- **Gateways**: None are present as specified.
  ![Base Infrastructure](vpc-peering-base.png "Base Infrastructure")

> 3.  Test Connectivity between VPCs
>
> - Ping from VPC1 public subnet to VPC2 public subnet.
> - Ping from VPC1 private subnet to VPC2 public subnet.
> - Ping from VPC1 private subnet to VPC2 private subnet.
> - Repeat tests from VPC2 to VPC1.

> 4.  Record observations and modify settings to enable all eight possible connections:
>     **Findings**:
>     With the current configuration it is not possible to communicate between the two VPCs. Accordingly, I also have no SSH access to the public and private instances in VPC2. Within VPC1 between private and public subnet, communication between the Ubuntu instances is possible (important: ICMP must be specified in Security Group).

**Solution**:
The VPC peering connection between the two VPCs is available in the basic infrastructure. However, specific routes between the subnets of both VPCs and the VPC peering connection are still required in order to enable successful traffic between the two VPCs, i.e. to enable communication between the instances. The basic infrastructure has been extended as follows:

- VP2: Add and associate route tables to the public and private subnet
- VPC1 & 2: Create routes between VPC Peering Connection and private & public subnets

**Findings after extension**:
Since the routes have been properly defined, all 8 connections between the VPCs are possible.

![Revised infrastructure](vpc-peering-solution.png "Revised infrastructure")

> 5.  Once you managed that all 8 possible connections happened, check if VPC2 can access the internet – It should not.
>     Instead of hooking it up to a new Internet Gateway OR the existing one – Try to figure a way for both (VPC2 private and public) to connect to the internet via VPC1 public subnet.

**Findings**
With VPC peering, resources in VPC2 cannot use the IGW of VPC1 to access the internet. This is because VPC peering establishes a private connection between the two VPCs, and does not provide any internet access capabilities ([Docs AWS - VPC peering limitations](https://docs.aws.amazon.com/vpc/latest/peering/vpc-peering-basics.html#vpc-peering-limitations)).

However, an alternative would be to use a transit gateway instead of a VPC peering connection.

## {{< highlight go >}}<b>Storage for your Architecture</b>{{< /highlight >}}<br>
| **Storage Type** | **Structure** | **Functionality** | **Organization Method** |
|-----------------|----------------|--------------------|------------------------|
| **Block Storage** | Consists of fixed-size storage blocks (typically ranging from 512 bytes to 64 kilobytes) each with a unique address. | Operating systems interact with block storage by requesting data blocks via interfaces like iSCSI or Fibre Channel. This allows fast, low-latency access, often used for performance-intensive applications such as databases. | Blocks are organized on physical storage media like HDDs or SSDs and can be aggregated through volume manager software into larger logical units. |
| **File Storage** | Organizes data in a hierarchical structure of files and directories, similar to the file system on a conventional computer. | Users and applications interact with file storage via standardized protocols like NFS or SMB/CIFS to read, write, and manage files. | Files are stored in a directory tree, allowing data to be organized and searched by name and path. File storage systems manage metadata such as access rights and timestamps. |
| **Object Storage** | Stores data as objects, which consist of three main components: the data content itself, metadata, and a unique ID (object ID). | Objects are accessed independently of a hierarchical file system via APIs (e.g., RESTful HTTP), enabling scalable and flexible storage solutions well-suited for cloud applications and big data analytics. | Objects are stored in a flat address space environment where each object is accessible via its ID. Object storage can extend metadata, facilitating detailed categorization and management of stored data. |

![Different Storage types](types-storage.png "Different Storage types")

### {{< highlight go >}}<b>EC2 Storage - Overview</b>{{< /highlight >}}<br>

In EC2 you can make use all types of storage mentioned above (Block, File & Object Storage).

- **Block**: Amazon EBS, Amazon EC2 Instance Storage
- **File**: Amazon EFS
- **Oject**: Amazon S3 & Glacier

#### {{< highlight go >}}<b>EC2 Instance Storage - Block Storage</b>{{< /highlight >}}<br>

- **Temporary Storage:** Specifically for EC2 instances, if the instance is wiped, the storage is also wiped.
- **Attachment:** Storage can only be attached to running instances and is neither detachable nor sharable between instances.
- **Location and Use:** Resides on the same physical host as the instance, ideal for caching and temporary data.
- **Volume Types:** Supports multiple volumes per instance, with options like HDD, SSD, or NVMe.

![EC2 Instance Storage](eis.png "EC2 Instance Storage")

#### {{< highlight go >}}<b>EBS (Elastic Block Storage) – Block Storage</b>{{< /highlight >}}<br>

![EBS](ebs.png "EBS")

- **Raw Block Devices:** Presented as unformatted devices that require formatting by the user.
- **Persistence:** Provides persistent storage that remains even if the instance is stopped.
- **Configurations:** Allows data deletion on detachment or instance termination; default setting.
- **Snapshots and Replication:** Enables snapshot creation, stored on S3, and can be restored to a new volume. Automatically replicated within its Availability Zone to enhance data security.
- **Multi-Instance Attachment:** Features EBS Multi-Attach for using a single volume on multiple instances.
- **Physical Storage:** Unlike instance storage, EBS is located on an external storage device, not on the host computer.

![EC2 Instance Storage](eis.png "EC2 Instance Storage")

#### {{< highlight go >}}<b>EFS (Elastic File System) – File Storage</b>{{< /highlight >}}<br>

- **Service Overview:** Amazon EFS offers a simple, serverless, elastic file system for AWS Cloud and on-premises resources, operating as a Platform-as-a-Service (PaaS).
- **Scalability:** Automatically scales to petabytes without disrupting applications, adjusting as files are added or removed.
- **Compatibility:** Supports NFSv4 protocol.
- **Performance Modes:**
  - _General Purpose:_ Best for latency-sensitive applications like web servers.
  - _Max I/O:_ Scales to higher throughput and operations per second, with increased latencies.
- **Throughput Modes:**
  - _Bursting Throughput:_ Throughput increases as file system size grows.
  - _Provisioned Throughput:_ Allows specification of throughput independent of data volume.
- **Storage Classes:**
  - _Standard:_ Offers multi-AZ resilience (EFS Standard and EFS Standard–IA).
  - _One Zone:_ For cost savings, stores data in a single AZ (EFS One Zone and EFS One Zone–IA).

![EFS](efs.png "EC2 Instance Storage")

#### {{< highlight go >}}<b>S3 (Simple Storage Service) – Object Storage</b>{{< /highlight >}}<br>

- **Functionality:** Provides object storage where files are stored as complete units.
- **Service Type:** Operates as a Platform-as-a-Service (PaaS), not Infrastructure-as-a-Service (IaaS).
- **Archival Storage:**
  - _Glacier:_ A lower-cost archival storage solution within S3 for long-term data retention.
  - _Cost Efficiency:_ Cheaper per GB stored compared to standard S3.
  - _Retrieval Cost and Time:_ Retrieval is more expensive and slower, with latencies extending to hours.
- **Integration and Durability:**
  - _Serverless:_ Ready-to-use at setup, integrates with EC2 for storing EBS snapshots.
  - _Mounting:_ S3 buckets can be mounted to EC2 instances.
  - _Durability:_ Offers high durability, globally accessible, not confined to specific regions.

![S3](s3.png "S3")

## {{< highlight go >}}<b>VPC Flow Logs</b>{{< /highlight >}}<br>

VPC Flow Logs capturing information about the IP traffic to and from network interfaces in a Virtual Private Cloud (VPC). These logs can be published to CloudWatch or S3 for further analysis and monitoring.

**Key Points:**

- Activated at the VPC or subnet level.
- Monitors all network interfaces within the specified scope.
- Logs can be stored in CloudWatch or S3.

### {{< highlight go >}}<b>Fields in VPC Flow Logs (Version 1 fields)</b>{{< /highlight >}}<br>

Each VPC Flow Log record is a string with fields separated by spaces. The fields provide information about the network traffic.

| Field Name   | Description                                            | Data Type |
| ------------ | ------------------------------------------------------ | --------- |
| version      | Version of the flow log format.                        | STRING    |
| account-id   | AWS account ID associated with the flow log.           | STRING    |
| interface-id | ID of the network interface.                           | STRING    |
| srcaddr      | Source IP address.                                     | STRING    |
| dstaddr      | Destination IP address.                                | STRING    |
| srcport      | Source port.                                           | INT       |
| dstport      | Destination port.                                      | INT       |
| protocol     | Protocol of the traffic (e.g., TCP, UDP).              | INT       |
| packets      | Number of packets in the flow.                         | INT       |
| bytes        | Number of bytes in the flow.                           | INT       |
| start        | Start time of the flow (Unix timestamp).               | INT       |
| end          | End time of the flow (Unix timestamp).                 | INT       |
| action       | Action associated with the traffic (ACCEPT or REJECT). | STRING    |
| log-status   | Status of the log (OK, NODATA, SKIPDATA).              | STRING    |

### {{< highlight go >}}<b>Advanced fields in VPC Flow Logs (Version 2 fields)</b>{{< /highlight >}}<br>

| Field Name          | Description                                                                                   | Data Type |
| ------------------- | --------------------------------------------------------------------------------------------- | --------- |
| flow-direction      | Direction of the flow (ingress or egress).                                                    | STRING    |
| traffic-path        | Path taken by the egress traffic (e.g., through an internet gateway, VPC peering connection). | STRING    |
| pkt-src-aws-service | Source AWS service if the source IP address belongs to an AWS service.                        | STRING    |
| pkt-dst-aws-service | Destination AWS service if the destination IP address belongs to an AWS service.              | STRING    |

### {{< highlight go >}}<b>Customizing Flow Logs</b>{{< /highlight >}}<br>

You can create custom formats for your Flow Logs. The default format includes all version 2 fields. Custom formats allow for the inclusion or exclusion of specific fields to tailor the logs to your needs.

**Example Custom Format:**

```
${version} ${account-id} ${interface-id} ${srcaddr} ${dstaddr} ${srcport} ${dstport} ${protocol} ${packets} ${bytes} ${start} ${end} ${action} ${log-status}
```

This example includes only the most essential fields, which can be expanded based on specific requirements.

### {{< highlight go >}}<b>Usage and Benefits</b>{{< /highlight >}}<br>

Enabling VPC Flow Logs can help with:

- **Security Monitoring**: Identifying suspicious activity and verifying security group and NACL rules.
- **Network Troubleshooting**: Diagnosing connectivity issues within the VPC.
- **Cost and Performance Optimization**: Analyzing data transfer costs and performance bottlenecks.

## {{< highlight go >}}<b>Network ACL (Access Control List)</b>{{< /highlight >}}<br>

A network access control list (ACL) is an optional layer of security on VPC and acts as a firewall for controlling traffic in and out of one or more subnets. You define rules like Source/Destination or Protocol that are allowed/denied. Default NACL is configured to allow all traffic In- and Egress.

![NACL](nacl.png "NACL")

## {{< highlight go >}}<b>Security Groups (SG)</b>{{< /highlight >}}<br>

Security groups act as virtual firewalls, controlling the incoming (ingress) and outgoing (egress) traffic for the resources they are associated with.

**Default Security Group:**

- **Ingress Rule**: By default, the default security group allows inbound traffic only from other resources that are associated with the same security group.
- **Egress Rule**: The default security group allows all outbound traffic, making it permissive for any destination outside the instances.

**Attaching Security Groups:**

Security groups are attached to individual resources within the VPC, such as EC2 instances, rather than being attached directly to the VPC itself.

## {{< highlight go >}}<b>Best Practice – Security Groups (SG) & NACL</b>{{< /highlight >}}<br>

**ACLs should not be used to control the traffic of your instance alone:**

- They should be used occasionally where you have specific compliance requirements, such as "We never allow SQL Ports from Subnet XYZ." Instead of configuring multiple security groups to block SQL, ensure it is covered in the NACL.

**NACL is complementary to Security Groups:**

- Define use-case specific rules inside your security groups.
- Only general, critical compliance rules that need to be consistently applied should be set inside the NACL.
- This approach ensures coverage of essential rules that might be overlooked in a specific security group.

**Security Groups should handle most traffic control:**

- Security groups should be the primary method for controlling traffic.

## {{< highlight go >}}<b>Reachability Analyzer</b>{{< /highlight >}}<br>

**Complexity with NACL and SGs:**

- The more you mix NACLs and SGs, the more complex it gets to troubleshoot.

**Tools for Troubleshooting:**

- To troubleshoot, you have certain tools – one of them is the Reachability Analyzer.
- For it, you need to have all VPC Flow Logs enabled.
- There you can define where traffic starts, where it turns, and where it ends.
- If any traffic was blocked on the way or something needs to be troubleshooted for other reasons, you'll see it inside the Analyzer.
- This way, you don't need to double-check SGs and NACLs if something's not working as intended. Instead, the Analyzer tells you where the issue resides.

## {{< highlight go >}}<b>Task 15 Network Security: Documenting the Reachability Analyzer Findings and Fixes</b>{{< /highlight >}}<br>

> With Terraform:
> Create a Security Group that allows SSH traffic from one public subnet instance to another – Ingress and Egress
> Create a Security Goup that does not specify SSH traffic for Ingress, only Egress
> Now we should have one side being able to communicate and the other not
> Create a NACL that allows all traffic (basic config) but denies ssh traffic
> Check with the Reachability Analyzer the SSH communication
> Document inside your blog the behavior. Now fix the issue showed by the Analyzer. Either NACL or the SG should now be appended and the other > issue should be still open. What happens now, if you analyze the same call? Document and fix it. Retry again.

### {{< highlight go >}}<b>Initial Basic Infrastructure from Earlier Task</b>{{< /highlight >}}<br>

Used base infrastructure from an earlier task, which included the following components:

- **VPC**: Created a Virtual Private Cloud (VPC).
- **Subnets**: Configured a public subnet and a private subnet within the VPC.
- **Internet Gateway (IGW)**: Attached an IGW to the VPC to allow internet access for the public subnet.
- **NAT Gateway**: Set up a NAT Gateway in the public subnet to enable instances in the private subnet to access the internet without exposing them directly.
- **Route Tables**: Created route tables to manage traffic between subnets, IGW, and NAT Gateway.
  - Public subnet route table included a route to the IGW.
  - Private subnet route table included a route to the NAT Gateway.
- **Security Groups**:
  - Initial security group allowing SSH access to instances in both public and private subnets.
- **Instances**:

  - Deployed an EC2 instance in the public subnet (act as a bastion (jump host) with SSH access.)
  - Deployed an EC2 instance in the private subnet.

### {{< highlight go >}}<b>Initial Setup</b>{{< /highlight >}}<br>

- **Security Groups:**

  - Created a security group (`allow_ssh`) allowing SSH traffic from one public subnet instance to another (ingress and egress).
  - Created a security group (`restrict_ssh`) that does not specify SSH traffic for ingress, only egress.

- **Network ACL (NACL):**

  - Configured a NACL allowing all traffic except for denying SSH traffic.

### {{< highlight go >}}<b>Reachability Analyzer Results</b>{{< /highlight >}}<br>

**Step 1: Initial Analysis**

- **Source:**

  - Instance: `i-03c1b6950b17edb3a` (public instance)
  - Security Group: `sg-00a3cb7eb355877bb` (allow_ssh_icmp_public)

- **Destination:**

  - Instance: `i-02c51466e6b22fe50` (private instance)
  - Security Group: `sg-0a1dbe3f7777c9dc9` (restrict_ssh)

- **NACL:**
  - NACL ID: `acl-01b3ec78dbc35d579` denies SSH traffic inbound.

**Findings:**

- Both the NACL and the private instance's security group were blocking SSH communication.

![Initial Reachability Analysis](ra1.png "Initial Reachability Analysis")

**Step 2: Adjusting Security Group**

- Added ingress rule to private instance security group to allow SSH traffic:
  ```hcl
  ingress {
      description = "SSH"
      from_port   = 22
      to_port     = 22
      protocol    = "tcp"
      cidr_blocks = ["0.0.0.0/0"]
  }
  ```

**New Findings:**

- Only the NACL was blocking SSH communication.

![Reachability Analysis After SG Adjustment](ra2.jpg "Reachability Analysis After SG Adjustment")

**Step 3: Adjusting NACL**

- Added ingress rules to NACL to allow SSH traffic:

  ```hcl
  # Allow SSH from public to private subnet
  ingress {
    rule_no    = 101
    protocol   = "tcp"
    action     = "allow"
    cidr_block = aws_subnet.my-subnet-public.cidr_block
    from_port  = 22
    to_port    = 22
  }

  # Allow SSH from private to public subnet
  ingress {
    rule_no    = 102
    protocol   = "tcp"
    action     = "allow"
    cidr_block = aws_subnet.my-subnet-private.cidr_block
    from_port  = 22
    to_port    = 22
  }
  ```

**Final Findings:**

- SSH communication was successfully established between the instances.

![Final Reachability Analysis](ra3.jpg "Final Reachability Analysis")

### {{< highlight go >}}<b>Summary</b>{{< /highlight >}}<br>

- Initially, both the NACL and the private instance's security group were blocking SSH communication.
- After adjusting the private instance's security group to allow SSH ingress, only the NACL was blocking the traffic.
- Finally, after adjusting the NACL to allow SSH traffic from cidr's public and private subnet, communication was successfully established.

## {{< highlight go >}}<b>Data In Transit vs. Data At Rest</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Data In Transit</b>{{< /highlight >}}<br>

Data in transit, or data in motion, refers to data actively moving from one location to another, such as across the internet or through a private network. Protecting data in transit involves securing this data while it's traveling between networks or being transferred from local storage to cloud storage. Effective data protection measures are critical during transit as data is often considered less secure while in motion.

### {{< highlight go >}}<b>Data At Rest</b>{{< /highlight >}}<br>

Data at rest is data that is not actively moving from device to device or network to network. This includes data stored on hard drives, laptops, flash drives, or archived in other ways. Data protection at rest aims to secure inactive data stored on any device or network. Although data at rest is sometimes viewed as less vulnerable, it is often a more valuable target for attackers.

### {{< highlight go >}}<b>The Role of Encryption</b>{{< /highlight >}}<br>

Data can be exposed to risks both in transit and at rest, requiring protection in both states. Encryption is a major tool for securing data in both conditions. For data in transit, encryption methods like HTTPS, SSL, TLS, and FTPS are used. For data at rest, sensitive files can be encrypted before storage, or entire storage drives can be encrypted.

### {{< highlight go >}}<b>Best Practices for Data Protection</b>{{< /highlight >}}<br>

Effective data protection methods include:

1. **Encryption**: Essential for both data in transit and at rest.
2. **Network Security Controls**: Use firewalls and network access control to protect data in transit.
3. **Proactive Security Measures**: Identify at-risk data and apply effective protection strategies.
4. **Data Protection Solutions**: Implement policies for user prompting, blocking, or automatic encryption.
5. **Data Classification Policies**: Categorize and classify company data to ensure appropriate protection measures.
6. **Cloud Vendor Evaluation**: Assess security measures offered by cloud providers, including access controls, encryption, and backup frequency.

### {{< highlight go >}}<b>Risk Profiles</b>{{< /highlight >}}<br>

The risk profiles for data in transit and data at rest depend on the security measures in place. While attackers may target valuable data in either state, a proactive approach including data classification and context-aware security protocols is most effective for comprehensive data protection.

### {{< highlight go >}}<b>Frequently Asked Questions</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>What is the difference between data at rest and data in transit?</b>{{< /highlight >}}<br>

Data at rest is stationary, stored on a device, while data in transit is actively moving between locations over a network. Data in transit is more vulnerable to interception and should be encrypted.

#### {{< highlight go >}}<b>What is an example of data in transit?</b>{{< /highlight >}}<br>

An example of data in transit is information transferred between a remote user’s mobile device and a cloud-based application. Encryption is crucial to protect such data from malicious actors.

#### {{< highlight go >}}<b>Is data encrypted in transit and at rest?</b>{{< /highlight >}}<br>

Data can be encrypted in both states. Encryption is not inherent and must be applied to protect data from unauthorized access.

#### {{< highlight go >}}<b>What are some data at rest examples?</b>{{< /highlight >}}<br>

Examples include spreadsheet files on a laptop's hard drive, videos on a mobile device, employment records in corporate HR applications, and sales data in company databases.

## {{< highlight go >}}<b>AWS: Encrypting Data-at-Rest and Data-in-Transit</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Overview</b>{{< /highlight >}}<br>

AWS recommends encryption as an additional access control to complement identity, resource, and network-oriented controls. AWS provides features for easy data encryption and key management. All AWS services offer encryption capabilities for data at rest and in transit, integrating with AWS Key Management Service (KMS) to control key lifecycle and permissions.

### {{< highlight go >}}<b>Data-at-Rest Encryption</b>{{< /highlight >}}<br>

AWS services use server-side encryption to ensure consistent and correct encryption application. Customers control data decryption, managing access through AWS KMS policies. This creates logical separation between data and key access. Customers can also use client-side encryption with AWS KMS for application-level encryption, ensuring consistent security across architectures, whether on AWS, on-premises, or hybrid.

#### {{< highlight go >}}<b>Hardware Security Modules (HSMs)</b>{{< /highlight >}}<br>

AWS KMS uses HSMs to protect customer keys. These HSMs are FIPS 140-2 validated and prevent unauthorized use of plaintext keys. Customer keys are isolated and can only be used within the AWS region where they were created. All AWS KMS actions are logged to AWS CloudTrail for auditing.

#### {{< highlight go >}}<b>AWS CloudHSM</b>{{< /highlight >}}<br>

For direct HSM management, AWS CloudHSM offers dedicated, FIPS 140-2 Level 3 validated HSMs. CloudHSM supports integration via PKCS#11, JCE, and CNG APIs, allowing key export for hybrid architectures. AWS automates administrative tasks, while customers manage scaling and crypto accounts within the HSM.

### {{< highlight go >}}<b>Data-in-Transit Encryption</b>{{< /highlight >}}<br>

AWS encrypts network traffic at multiple levels:

- **Physical Layer**: Encryption between AWS data centers.
- **Network Layer**: Encryption within VPCs and peered VPCs using supported EC2 instances.
- **Application Layer**: Encryption using protocols like TLS, with all AWS endpoints supporting TLS for secure HTTPS connections.

#### {{< highlight go >}}<b>Terminating TLS Connections</b>{{< /highlight >}}<br>

AWS provides options for terminating TLS connections:

- **Load Balancing Services**: Elastic Load Balancing, Network Load Balancer, Application Load Balancer.
- **Amazon CloudFront**: Content delivery network.
- **Amazon API Gateway**: Secure API requests.

AWS Certificate Manager (ACM) simplifies the management of digital certificates, providing publicly trusted certificates at no cost and offering a private certificate authority for internal communication.

### {{< highlight go >}}<b>Comprehensive Encryption Strategy</b>{{< /highlight >}}<br>

Using AWS KMS, CloudHSM, and ACM, customers can implement a comprehensive encryption strategy for data at rest and in transit, ensuring consistent security for data across the AWS ecosystem.

## {{< highlight go >}}<b>Task: Data Encryption Concept for AWS Infrastructure</b>{{< /highlight >}}<br>

We are working with the basic infrastructure implemented in Tasks 10-13. Currently, there is no encryption configured for the root EBS volume, additional EBS volumes, EFS, or S3 bucket. This concept aims to change that by implementing encryption. With EBS and EFS, the options for encryption are AWS managed (KMS abstracted) or via KMS itself. With S3 you have 3 different options:

- SSE-C: Server-side encryption with customer-provided keys.
- SSE-S3: Server-side encryption with Amazon S3-managed keys (default).
- SSE-KMS: Server-side encryption with AWS KMS keys.
  I decided to go with the AWS managed approach for all three services.

### {{< highlight go >}}<b>Encryption Considerations</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>Encryption in Transit</b>{{< /highlight >}}<br>

Encryption in transit is essential to protect data as it moves between clients, services, and AWS infrastructure. It prevents the interception and manipulation of data by ensuring the security of data during transmission over the network.

In this context, encryption in transit should be applied to:

- Data transfers between EC2 instance and EFS (TLS protected, configured during mount)
- Data transfers between EC2 instance and S3 bucket (here via awscli [aws s3 sync] -> https protected, that means via SSL/TLS)

#### {{< highlight go >}}<b>Encryption at Rest</b>{{< /highlight >}}<br>

Encryption at rest protects data stored on AWS services. It ensures data is unreadable to unauthorized users and complies with regulatory requirements.

In this context, encryption at rest should be applied to:

- Root EBS volume
- Additional EBS volumes
- EFS
- S3 buckets

### {{< highlight go >}}<b>Encryption Concept</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>Root EBS Volume Encryption</b>{{< /highlight >}}<br>

| Aspect          | Description                                                       |
| --------------- | ----------------------------------------------------------------- |
| Service         | EBS                                                               |
| Encryption Type | AWS managed (using default KMS keys)                              |
| Implementation  | Configure during instance launch, ensure root volume is encrypted |

#### {{< highlight go >}}<b>Additional EBS Volume Encryption</b>{{< /highlight >}}<br>

| Aspect          | Description                                                           |
| --------------- | --------------------------------------------------------------------- |
| Service         | EBS                                                                   |
| Encryption Type | AWS managed (using default KMS keys)                                  |
| Implementation  | Configure during volume creation, attach encrypted volume to instance |

#### {{< highlight go >}}<b>EFS Encryption</b>{{< /highlight >}}<br>

| Aspect          | Description                                                   |
| --------------- | ------------------------------------------------------------- |
| Service         | EFS                                                           |
| Encryption Type | AWS managed (using default KMS keys)                          |
| Implementation  | Enable encryption during EFS creation, configure mount target |

#### {{< highlight go >}}<b>S3 Bucket Encryption</b>{{< /highlight >}}<br>

| Aspect          | Description                                                           |
| --------------- | --------------------------------------------------------------------- |
| Service         | S3                                                                    |
| Encryption Type | AWS managed (S3 default encryption using S3-managed keys or KMS keys) |
| Implementation  | Enable default encryption on the S3 bucket                            |

#### {{< highlight go >}}<b>Implementation of Encryption</b>{{< /highlight >}}<br>

See in `task-16-data-encryption` in files `efs-and-s3` & `instance-and-ebs`.

## {{< highlight go >}}<b>What is a Container</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Definition</b>{{< /highlight >}}<br>

“A container is a standard unit of software that packages up code and all its dependencies so the application runs quickly and reliably from one computing environment to another” – Docker.

### {{< highlight go >}}<b>Key Concepts</b>{{< /highlight >}}<br>

- **Abstraction**: Containers eliminate the need for hypervisors and operating systems (OSs) by encapsulating the application and its dependencies. This allows running applications designed for one OS on another OS (e.g., a Windows application on Linux).
- **Configuration**: Containers allow you to configure the container image once and run it anywhere, ensuring consistent behavior across different environments.

### {{< highlight go >}}<b>Container Image Components</b>{{< /highlight >}}<br>

- **Code**: The application code.
- **Runtime**: The environment where the code runs.
- **System Tools**: Utilities required for the application.
- **System Libraries**: Libraries that the application depends on.
- **Settings**: Configuration settings for the application.

### {{< highlight go >}}<b>Tools for Managing Containers</b>{{< /highlight >}}<br>

- **Docker**: A widely used platform for developing, shipping, and running applications inside containers.
- **Packer**: A tool for creating machine and container images for multiple platforms from a single source configuration.
- **Windows Containers**: Containers designed to run Windows applications, enabling the use of containers on Windows OS.

### {{< highlight go >}}<b>Benefits</b>{{< /highlight >}}<br>

- **Portability**: Applications can run consistently across various environments without modification.
- **Efficiency**: Containers share the host OS kernel, making them more lightweight and efficient compared to traditional virtual machines (VMs).
- **Scalability**: Containers can be quickly scaled up or down to meet demand.

container.png
![VM's vs Container](container.png "VM's vs Container")

## {{< highlight go >}}<b>Amazon Elastic Container Registry (Amazon ECR)</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Overview</b>{{< /highlight >}}<br>

Amazon Elastic Container Registry (Amazon ECR) is a managed container image registry service provided by AWS. It supports private repositories with resource-based permissions using AWS IAM.

| Feature                 | Description                                                                                   |
| ----------------------- | --------------------------------------------------------------------------------------------- |
| **Compatibility**       | Supports Docker images, Open Container Initiative (OCI) images, and OCI compatible artifacts. |
| **CLI Support**         | Allows use of preferred CLI tools for managing images.                                        |
| **Public Repositories** | Supports public container image repositories as well.                                         |

### {{< highlight go >}}<b>Usage</b>{{< /highlight >}}<br>

- **Pushing Images**: Use CLI tools to push Docker and OCI images to Amazon ECR.
- **Pulling Images**: Retrieve images from Amazon ECR for local development or deployment.
- **Integration**: Integrate Amazon ECR images with Amazon ECS and Amazon EKS for container orchestration.

### {{< highlight go >}}<b>Components of Amazon ECR</b>{{< /highlight >}}<br>

| Component               | Description                                                                                                                              |
| ----------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Registry**            | Each AWS account gets a private registry for creating multiple repositories to store container images.                                   |
| **Authorization Token** | Clients authenticate to private registries as AWS users to push and pull images.                                                         |
| **Repository**          | Contains Docker images, OCI images, and OCI compatible artifacts.                                                                        |
| **Repository Policy**   | Controls access to repositories and their contents.                                                                                      |
| **Image**               | Container images can be pushed and pulled for local development or use in Amazon ECS task definitions and Amazon EKS pod specifications. |

## {{< highlight go >}}<b>Amazon Elastic Container Service (ECS)</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Overview</b>{{< /highlight >}}<br>

Amazon Elastic Container Service (ECS) is a service that runs containers on AWS. It provides two options for managing and running containers: using EC2 instances or the serverless Fargate platform.

### {{< highlight go >}}<b>ECS Options</b>{{< /highlight >}}<br>

| Option      | Description                                       | When to Use                                  |
| ----------- | ------------------------------------------------- | -------------------------------------------- |
| **EC2**     | Configure and launch containers on EC2 instances. | - High CPU and memory usage                  |
|             |                                                   | - Large workloads optimized for price        |
|             |                                                   | - Applications needing persistent storage    |
|             |                                                   | - Direct infrastructure management           |
| **Fargate** | Serverless solution to launch containers.         | - Large workloads optimized for low overhead |
|             |                                                   | - Small workloads with occasional bursts     |
|             |                                                   | - Tiny workloads                             |
|             |                                                   | - Batch workloads                            |

### {{< highlight go >}}<b>Details</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>ECS with EC2</b>{{< /highlight >}}<br>

- **Configuration**: You configure and manage the EC2 instances where the containers run.
- **Use Cases**: Suitable for workloads with consistent high CPU and memory usage, large workloads needing cost optimization, applications requiring persistent storage, and scenarios where direct infrastructure management is preferred.

#### {{< highlight go >}}<b>ECS with Fargate</b>{{< /highlight >}}<br>

- **Serverless**: AWS manages the infrastructure, and you only need to define and manage the containers.
- **Use Cases**: Ideal for large workloads optimized for low overhead, small workloads with occasional bursts, tiny workloads, and batch processing tasks.
