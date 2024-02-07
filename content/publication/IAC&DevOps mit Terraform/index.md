---
title: "DevOps and Automation Module"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2023-08-25"
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
summary: Beside the the school we have to complete different modules in our company. This publication is about IaC & DevOps (with Terraform)

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
  caption: 'Image credit: [**Adobe Stock: ArtemisDiana**](https://adobe.ly/3KWGRwp)'
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
# DevOps and Automation Module

## Day 1 - Module 01: Introduction to DevOps

### What is DevOps?
DevOps merges cultural philosophies, practices, and tools to enhance an organization's ability to deliver applications and services at high velocity, outpacing organizations with traditional development and infrastructure management processes. This synergy of development and operations aims for a continuous delivery model emphasizing repeatability, reliability, stability, resilience, and security, alongside operational efficiency improvements.

![DevOps](devops.jpg "DevOps")

#### DevOps Culture
The essence of DevOps culture lies in eliminating the barriers between development and operations teams, fostering an environment where both work in unison to amplify productivity and operational reliability. The movement's core values are encapsulated in the mantra "People over Process over Tools" and include:
- Culture
- Automation
- Measurement
- Sharing

These values guide the practical benefits of DevOps principles, allowing for frequent code deployments and the creation of resilient, self-healing systems equipped with advanced monitoring and alerting capabilities.

### Benefits of DevOps and AWS Tooling
DevOps practices enable organizations to deploy code multiple times a day, significantly reducing outages and downtime through the use of resilient systems. AWS services further enhance DevOps practices by providing tools that support continuous integration and delivery, infrastructure automation, and a consistent approach across projects.

![DevOps Tooling by AWS](devops-tooling-aws.jpg "DevOps Tooling by AWS")

#### Continuous Integration and Delivery Pipeline
Key components include:
- **Continuous Integration (CI):** Regularly merging code changes into a central repository to run automated builds and tests.
- **Automation:** Minimizing risks associated with manual processes by automating infrastructure management, which is achieved through Infrastructure as Code (IaC) and layered architecture designs.

![Components DevOps](components-devops.jpg "Components of DevOps Practise")


## Day 2 - Module 02: Infrastructure as Code (IaC) Overview

### Understanding IaC
Infrastructure as Code is a paradigm that manages and provisions infrastructure through code rather than manual processes, promoting reliability, reproducibility, and documentation. IaC tools range from ad hoc scripts for single-use tasks to configuration management tools like Chef, Puppet, Ansible, and SaltStack, which automate software installation on servers.

Below is an overview of the different types of tools used in IaC.

### Ad Hoc Scripts
Ad hoc scripts are simple, often improvised commands or sets of commands that are used to perform a specific task on one or more servers. They are the most basic form of automation, providing a quick and easy way to get things done without the need for more complex tooling. However, they can become difficult to manage and scale as infrastructure grows and changes.

![Ad Hoc Scripts](ad-hoc-scripts.jpg "Ad Hoc Scripts")

### Configuration Management Tools
Configuration management tools automate the process of controlling and tracking changes in the software, and ensuring that it is consistent and maintains its integrity over time. They can install and manage software on existing servers, enforce desired states, and automate routine tasks.

![Configuration Management Tools](conf-manage-tools.jpg "Configuration Management Tools")

#### Examples of Configuration Management Tools:
- **Chef**: A powerful automation platform that transforms infrastructure into code, allowing servers to be automatically set up and managed across a network.
- **Puppet**: Puppet manages infrastructure as code, automating the configuration and management of machines and the software running on them.
- **Ansible**: A simple, yet powerful, server and configuration management tool with a focus on simplicity and ease of use. It uses playbooks to describe automation jobs, and SSH for communication with servers.
- **SaltStack**: SaltStack is designed for IT automation, system and configuration management, and orchestrating complex software-defined data center environments.

### Server Templating Tools
Server templating tools are used to create images of server configurations, which can be rapidly deployed. This allows for the creation of consistent, repeatable server setups that can be quickly spun up or down as needed.

![Server Templating Tools](server-templating.jpg "Server Templating Tools")

#### Examples of Server Templating Tools:
- **Docker**: Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.
- **Packer**: Packer automates the creation of any type of machine image. It embraces modern configuration management by encouraging you to use automated scripts to install and configure the software within your Packer-made images.
- **Vagrant**: Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize productivity and flexibility.

### Server Provisioning Tools
Server provisioning tools are responsible for the initial setup of servers. They can create servers, install operating systems, and then hand them off to configuration management tools for further setup.

![Server Provisioning Tools](server-provisioning-tools.jpg "Server Provisioning Tools")

#### Examples of Server Provisioning Tools:
- **Terraform**: Terraform is an open-source infrastructure as code software tool created by HashiCorp. It enables users to define and provision a data center infrastructure using a declarative configuration language.
- **CloudFormation**: AWS CloudFormation provides a common language for you to model and provision AWS and third-party application resources in your cloud environment.

## Day 3 - Module 03: CloudFormation and AWS CDK

### CloudFormation: AWS's IAC Solution
CloudFormation, an AWS-native tool, facilitates infrastructure orchestration using JSON or YAML templates, enabling immutable infrastructures and providing a GUI for parameter configuration.

#### Differences Between CloudFormation and Terraform
CloudFormation is exclusive to AWS and offers built-in state management and direct support from AWS, though it lacks the modularization and flexibility found in Terraform.

### AWS Cloud Development Kit (CDK)
The CDK allows for defining cloud infrastructure using familiar programming languages and provisions it through CloudFormation. It supports modular, reusable code constructs, facilitating easier management, collaboration, and version control of cloud infrastructure.

#### CDK Concepts
Key concepts include Constructs (basic building blocks), Apps (root constructs), Stacks (units of deployment), and Environments (target deployment accounts and regions). The CDK enhances infrastructure management through features like logical expressions, high-level abstractions, and language independence.
