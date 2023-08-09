---
title: "Cloud Security"

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
## {{< hl >}}<b>Cloud Security in AWS</b>{{< /hl >}}<br>
In this module I will learn about Cloud Security in AWS. Here you will find several tasks or summarizations about the topic.<br>

## Day 1 Basics
Security is the practice of safeguarding intellectual property from unauthorized access, use, or modification.

The CIA triad is a fundamental concept in information security, comprising three core principles:
- Confidentiality: Limiting access to information to authorized users and preventing access by unauthorized persons.
- Integrity: Ensuring the consistency, accuracy, and trustworthiness of data throughout its lifecycle, including the origin or source of the data.
- Availability: Ensuring that information resources are readily accessible when needed.

The CIA triad faces challenges in modern IT environments due to the large volume of information to be protected, the diverse sources of data, and the variety of formats used.

`Security in the AWS cloud`<br>
 AWS tries to make security as familiar as what we are doing day by day. Security is of utmost importance, especially in a cloud environment.
Existing security models used in on-premises environments can be applied to the cloud.
AWS offers various services and tools to enhance security, providing <b>controllability</b>, <b>auditability</b>, and <b>visibility</b> into cloud resources and workloads.
The ability to work in an <b>agile</b> way and <b>automate</b> processes is especially important for incident response.<br>

`Security design principles`<br>
- least privilege
- enable traceability
- secure all layers
- automate security
- protect data in transit and at rest
- prepare for security events
- minimize attack surface

`AWS Well-Architected Framework`<br>
AWS follows the Shared Responsibility model (SRM), where responsibilities are divided between AWS and its customers.

![SRM](srm.jpg "<b> AWS Shared Responsibilty model |</b> Screenshot")<br>

AWS is responsible for safeguarding the global infrastructure that hosts all AWS Cloud services, including hardware, software, networking, and facilities.
As an AWS customer, you can securely provision various resources in the AWS Cloud, such as virtual machines, storage, databases, and desktops.
Customers are responsible for securing their data, operating systems, networks, platforms, and other resources created in the AWS Cloud.
Customers are accountable for maintaining the confidentiality, integrity, and availability of their data in the cloud, and for meeting specific business and compliance requirements for their workloads.

The division of responsibilities varies depending on the type of AWS services used, implying different levels of responsibility for AWS and the customers.<br>

`Authentication vs. Authorization`<br>
- Authentication is the process of identifying the users and validating who they claim to be.
- Authorization is the process (after authentication) to give the user access to specific resources (mostly role-based)

`AWS Identity and Access Management (IAM)`<br>
`Amazon Cognito for Authentication`<br>
