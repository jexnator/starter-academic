---
title: "Cloud Security in AWS"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2023-08-07"
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
summary: Beside the the school we have to complete different modules in our company. This publication is about Cloud Security

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash: Nathy dog**](https://unsplash.com/photos/z1uDmJx3ZEQ)'
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
In this module I will learn about Cloud Security in AWS. Here you will find several tasks or summarizations about the topic.<br>
<br>

## {{< hl >}}<b>Section 1: Course Introduction</b>{{< /hl >}}<br>
Security is the practice of safeguarding intellectual property from unauthorized access, use, or modification.

The CIA triad is a fundamental concept in information security, comprising three core principles:
- <b>Confidentiality</b>: Limiting access to information to authorized users and preventing access by unauthorized persons.
- <b>Integrity</b>: Ensuring the consistency, accuracy, and trustworthiness of data throughout its lifecycle, including the origin or source of the data.
- <b>Availability</b>: Ensuring that information resources are readily accessible when needed.

The CIA triad faces challenges in modern IT environments due to the large volume of information to be protected, the diverse sources of data, and the variety of formats used.

### {{< hl >}}<b>Security in the AWS cloud</b>{{< /hl >}}<br>
AWS tries to make security as familiar as what we are doing day by day. Security is of utmost importance, especially in a cloud environment.
Existing security models used in on-premises environments can be applied to the cloud.
AWS offers various services and tools to enhance security, providing <b>controllability</b>, <b>auditability</b>, and <b>visibility</b> into cloud resources and workloads.
The ability to work in an <b>agile</b> way and <b>automate</b> processes is especially important for incident response.

### {{< hl >}}<b>Security design principles</b>{{< /hl >}}<br>
- least privilege
- enable traceability
- secure all layers
- automate security
- protect data in transit and at rest
- prepare for security events
- minimize attack surface

### {{< hl >}}<b>AWS Well-Architected Framework</b>{{< /hl >}}<br>
AWS follows the Shared Responsibility model (SRM), where responsibilities are divided between AWS and its customers.
![SRM](srm.jpg "<b> AWS Shared Responsibilty model |</b> Screenshot")

AWS is responsible for safeguarding the global infrastructure that hosts all AWS Cloud services, including hardware, software, networking, and facilities.
As an AWS customer, you can securely provision various resources in the AWS Cloud, such as virtual machines, storage, databases, and desktops.
Customers are responsible for securing their data, operating systems, networks, platforms, and other resources created in the AWS Cloud.
Customers are accountable for maintaining the confidentiality, integrity, and availability of their data in the cloud, and for meeting specific business and compliance requirements for their workloads.

The division of responsibilities varies depending on the type of AWS services used, implying different levels of responsibility for AWS and the customers.
<br>
<br>

## {{< hl >}}<b>Section 2: IaM</b>{{< /hl >}}<br>
### {{< hl >}}<b>Authentication vs. Authorization</b>{{< /hl >}}<br>
- Authentication is the process of identifying the users and validating who they claim to be.
- Authorization is the process (after authentication) to give the user access to specific resources (mostly role-based)

### {{< hl >}}<b>AWS Identity and Access Management (IaM) Recap</b>{{< /hl >}}<br>
AWS uses IaM for authentication and authorization in the cloud. The following entities are relevant:
- Users: Indentity with long term credentials (pw/access key)
- Groups: A collection of users, apply permissions to a collection of users
- Roles: Identity with short term credentials, can be assumed by entities like users, services, accounts etc.
- Policies: An object in AWS that defines permissions (on AWS resources), can be attached to users, groups and roles
<br>

### {{< hl >}}<b>Amazon Cognito for Authentication</b>{{< /hl >}}<br>
Amazon Cognito is a service from AWS that provides authentication, authorization, and user management for web and mobile applications. It consists of two main components: User Pools and Identity Pools.

A user pool serves as a user directory that manages the login and registration process for an application. Users can sign in either directly through a user pool, or federate through a third-party identity provider (IdP). The main purpose of a user pool is the authentication of users by storing user data and providing users with access tokens. User Pools are not directly associated with AWS resources and do not handle the authorization of AWS services (directly).
![user pool workflow](user-pool.jpg "<b> user pool workflow |</b> Screenshot")

An Identity Pool allows temporary AWS credentials to be assigned to users (authenticated or unauthenticated) for example from a user pool, or other IdPs to grant access to AWS resources. An Identity Pool is focused on authorizing and managing AWS credentials.
![identity pools](identity-pools.jpg "<b> identity pools |</b> Screenshot")

<b>Different example use cases:</b>
| **example App**                 | **pool?** | **Description**                                                                                                                                    | **Solution**                                                                                                                                                                                                                                                                        |
|---------------------------------|--------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Blogging platform               | User pool                      | A blogging platform where users can write articles, comment and manage their profiles.                                        | A user pool is ideal for handling user registration and authentication. Users can log in, reset their password, and update their profiles. Since the interactions are mainly at the application level and do not require direct AWS permissions, an Identity Pool is not necessary. |
| Guest access to news app        | Identity pool                  | A news app where unauthenticated users (guests) can read articles and watch videos from a media archive.                      | An Identity Pool can be used to grant temporary AWS permissions to guests to access media content in AWS services. Since there is no authentication requirement for access, no user pool is needed.                                                                                 |
| Photo sharing app               | both                           | A mobile photo sharing app where users can upload their photos, which are stored in an S3 bucket, and share them with others. | A User Pool authenticates users and manages their credentials. After successful authentication, the Identity Pool provides temporary AWS permissions that allow the authenticated user to upload or download photos in an S3 bucket.                                                |

<br>

## {{< hl >}}<b>Section 3: Detective Controls</b>{{< /hl >}}<br>
![Monitoring Overview](monitoring-overview.jpg "<b> AWS Monitoring Overview |</b> Screenshot")

### {{< hl >}}<b>Amazon GuardDuty for Threat Detection</b>{{< /hl >}}<br>
Amazon GuardDuty is an intelligent threat detection service for AWS accounts and workloads. It uses threat intelligence and machine learning to detect anomalies and suspicious activities, such as unauthorized deployments. When a threat is found, alerts are sent to the GuardDuty console and AWS CloudWatch Events for integration with existing services or systems.
![GuardDuty detection categories](detection-categories.jpg "<b> GuardDuty detection categories |</b> Screenshot")

### {{< hl >}}<b>AWS Security Hub for Prioritizing Findings</b>{{< /hl >}}<br>
AWS Security Hub is a consolidated view of security. It uses different AWS services as inputs (e.g. GuardDuty, Macie, Firewall Manager, etc.). It also support third party insights. In security hub you have the possibility to evaluate the security in the cloud with different securiry standards. The insights and findings can be forwarded to EventBridge for incident responses.
![AWS Security Hub](security-hub.jpg "<b> AWS Security Hub Overview |</b> Screenshot")

### {{< hl >}}<b>Amazon Macie for Data Monitoring</b>{{< /hl >}}<br>
Amazon Macie can be used to analyze S3 buckets for sensitive data such as names, addresses, and credit card numbers. It also evaluates whether an S3 bucket is publicly accessible and whether it is encrypted or not. The analyses are be performed as jobs. They can be shedulded on personal preferences. The results can be published to security hub or even to event bridge to take action in an automated way.
![Amazon Macie](macie.jpg "<b> Example workflow with Macie |</b> Screenshot")
<br>

## {{< hl >}}<b>Section 4: Infrastructure Protection</b>{{< /hl >}}<br>
### {{< hl >}}<b>Securing Your Compute Resources</b>{{< /hl >}}<br>
In AWS you have different opportunities to limit access to resources on the network level. The most common ways are:
- Firewall on the host (e.g. netfilter on linux)
- Security Groups
- Subnet access control lists
- Web application firewall (WAF)
- Network firewall
- ...
![Securing compute resources on AWS](securing-resources.jpg "<b> Securing compute resources on AWS |</b> Screenshot")

### {{< hl >}}<b>WAF for Traffic Filtering</b>{{< /hl >}}<br>
A web application firewall operates at layer 7 and is capable of filtering the http protocol. The most common method of catching violations is to block requests or block them above a certain threshold. Possible filter rules are:
- filtering based on headers
- Query parameters
- HTTP-Methods
- URI path
- IPs
- http body (e.g. strings, size or SQL injection)

### {{< hl >}}<b>AWS WAF</b>{{< /hl >}}<br>
AWS WAF is a Web Application Firewall managed by AWS and is organized in Web Access Control Lists (Web ACLs). Web ACLs can be associated with different AWS services like:
- ALBs
- API Gateways
- AppSync
- CloudFront

After a WAF is associated, every request gets checked based on the configured rules.
   
### {{< hl >}}<b>AWS Shield for DDoS Protection</b>{{< /hl >}}<br>
AWS Shield is a managed DDoS protection service that safeguards web applications that run on AWS. AWS Shield provides always-on detection and automatic inline mitigations that minimize application downtime and latency.
<br>
<br>

## {{< hl >}}<b>Section 5: Data Protection</b>{{< /hl >}}<br>
### {{< hl >}}<b>Amazon S3 spotlight</b>{{< /hl >}}<br>
Amazon S3 is an object storage service in AWS that enables storage, retrieval, and management of data in the cloud. It uses a flat namespace schema with buckets and keys and provides API access for CRUD operations. It is used for static websites, backups, archiving, and data analytics etc.
-S3 data is fully private to an account, and public access is blocked by default 
- Ability to encrypt your data and have AWS manage the keys

### {{< hl >}}<b>S3 Protection via resource-based policies</b>{{< /hl >}}<br>
<b>Default Privacy and Access Control:</b>
Amazon S3 resources are private by default, only accessible by the owner. Access can be controlled through policies and Access Control Lists (ACLs).

<b>Types of Access Control Mechanisms:</b>
Amazon S3 supports two groups of access control: resource-based (bucket policies, bucket ACLs, object ACLs) and user-based (IAM user policies). ACLs grant read or write access to groups of users. Policies enable centralized management.

<b>Bucket Policies:</b>
Bucket policies in Amazon S3 can add or deny permissions within a single bucket. They allow for flexibility in granting access to users within your AWS Account or other AWS accounts, centralizing the control of permissions.

<b>Use cases</b>

Object ACLs:
- Grant access to individual objects
- Access objects owned by another account

Bucket ACLs:
- Grant log delivery group write permissions to bucket

Bucket policies:
- Offer a larger range of permissions than bucket ACLs
- Provide cross-account access to bucket

IAM identity-based policies:
- Manage permissions by creating users and groups and attaching policies

### {{< hl >}}<b>Protection via encryption</b>{{< /hl >}}<br>
#### {{< hl >}}<b>Encryption primer</b>{{< /hl >}}<br>
![Encryption primer](encryption-primer.jpg "<b> Encryption primer |</b> Screenshot")

Data encryption is typically done using a symmetric data key generated by software or hardware, preferable for encrypting large amounts of data. This key is applied to the data using an algorithm like AES, resulting in indistinguishable ciphertext. The encrypted data can be stored on platforms like AWS or on-premises.

To decrypt the data, the symmetric data key must be available to authorized users. It can't be stored with the encrypted data as it would compromise security. The best practice is to encrypt the symmetric data key with a KMS key, allowing it to be stored with the encrypted data in the same location, maintaining similar durability characteristics.

#### {{< hl >}}<b>Supported Encryption by Amazon S3</b>{{< /hl >}}<br>
Amazon S3 supports Client-side encryption (CSE) and Server-side encryption (SSE). CSE means that the customer encrypts his data by self with an Encryption Software and then publish it to AWS. If you use Server-side encryption then AWS manages the encryption and decryption proccess. Each approach has its own advantages.

When selecting the right enryption solution for data in AWS then three question should be come up:
- Where will the keys be stored? Will they be stored by your own hardware or using hardware provided by AWS?
- Where will the keys be used? Will they be used by the client software or on AWS? 
- Who will manage the keys? Do you want to assign user- or application-level permissions or have AWS manage permissions?

![Supported Enryption in AWS](s3-encryption.jpg "<b> Supported Enryption in AWS |</b> Screenshot")

##### {{< hl >}}<b>S3 Client-side encryption</b>{{< /hl >}}<br>
Only the encrypted version of the data is stored in S3, ensuring that AWS never sees the unencrypted content. The client maintains the keys and ecrypts and decrypts the data with 
![CSE](cse.jpg "<b> Client-Side encryption |</b> Screenshot")

##### {{< hl >}}<b>S3 Server-side encryption: Three different approaches</b>{{< /hl >}}<br>
With SSE-C in Amazon S3, you provide an encryption key for S3 to handle encryption and decryption. You manage only this key, not the encryption process. S3 doesn't store your key but keeps a salted HMAC value to validate requests. This HMAC can't decrypt data. If you lose the key, you lose access to the object.
![SSE-C](sse-c.jpg "<b> SSE-C |</b> Screenshot")

SSE-S3 is an AWS managed approach. Amazon S3 encrypts each object with a unique key. As an additional safeguard, it encrypts the key itself with a Primary key that it rotates regularly. Amazon S3 server-side encryption uses one of the strongest block ciphers available to encrypt your data, 256-bit Advanced Encryption Standard (AES-256).
![SSE-S3](sse-s3.jpg "<b> SSE-S3 |</b> Screenshot")

SSE-KMS encrypts Amazon S3 objects using AWS KMS keys, offering greater benefits than SSE-S.
AWS KMS employs envelope encryption with two keys:
- a data key for object encryption
- a master AWS KMS key for the data key's encryption.
This process enhances security against unauthorized access. With SSE-KMS, users get an audit trail of key usage in CloudTrail, the choice to create or use a default encryption key, and the ability to enforce key policies and import personal key material, granting more control than SSE-S3.
![SSE-KMS](sse-kms.jpg "<b> SSE-KMS |</b> Screenshot")

##### {{< hl >}}<b>Best practices for protecting data in Amazon S3</b>{{< /hl >}}<br>
- Enforce encryption at rest.
- Separate data based on different classification levels.
- Review S3 bucket and object permissions regularly.
- Define your data retention requirements.
- Implement secure key management.

### {{< hl >}}<b>AWS Key Management Service (KMS)</b>{{< /hl >}}<br>
AWS KMS is a managed service that lets you create, control, and securely store encryption keys using FIPS 140-2 validated hardware. Integrated with most AWS services, it employs envelope encryption and a two-tiered key hierarchy. You can encrypt/decrypt data under keys you control, set key usage policies, and monitor usage through AWS CloudTrail. The key never leaves AWS KMS, minimizing data key compromise risks.

When hardware is FIPS 140-2 (Federal Information Processing Standard Publication 140-2) validated, it means the hardware has undergone a rigorous testing process and is approved to be used in government and regulated industries for securing sensitive or classified information.

![KMS](kms.jpg "<b> KMS exmaple with EBS|</b> Screenshot")
1. Amazon EBS obtains an encrypted data key under a CMK through AWS KMS and stores the encrypted key with the volume metadata.
2. Encrypted data key is retrieved from storage by the servers that host EC2 instances.
3. A call is made to AWS KMS over SSL to decrypt the encrypted data key. AWS KMS identifies the CMK, makes an internal request to an HSA in the fleet to decrypt the data key, and returns the key back to the customer over the SSL session.
4. The decrypted data key is stored in memory and used to encrypt and decrypt all data going to and from the attached EBS volume. Amazon EBS retains the encrypted data key for later use in case the data key in memory is no longer available.

### {{< hl >}}<b>HTTPS - CA - SSL Certificate</b>{{< /hl >}}<br>
![CSR](ca.jpg "<b> CSR Workflow |</b> Screenshot")
![SSC](ssc.jpg "<b> self-signed certificate |</b> Screenshot")

### {{< hl >}}<b>AWS Certificate Manager (ACM) for Securing Communicationsn</b>{{< /hl >}}<br>
AWS Certificate Manager (ACM) lets you easily provision, manage, and deploy public and private Secure Sockets Layer/Transport Layer Security (SSL/TLS) certificates for use with AWS services and your internal connected resources. With ACM, you no longer need to spend time purchasing, uploading, and renewing SSL/TLS certificates manually. This makes it simpler to secure your applications and services with SSL/TLS encryption and ensures that your certificates are always up-to-date.

### {{< hl >}}<b>AWS Secrets Manager for Credentials Management</b>{{< /hl >}}<br>
