---
title: "DevOps and Automation Module"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2024-02-08"
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
{{< toc >}}

# DevOps and Automation Module
## Introduction to DevOps

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


## Infrastructure as Code (IaC) Overview

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

### Procedural Language vs. Declarative Language Definition

Procedural languages are characterized by their focus on the sequence of operations to perform a task. They do not inherently capture the complete state of the infrastructure, making it difficult to understand the deployment's current state without knowing the order in which scripts or templates were executed. This sequential nature also limits the reusability of procedural code, as adjustments must often be made based on the infrastructure's existing state.

Procedural languages: Chef & Ansible

In contrast, declarative languages, as used in tools like CloudFormation and Terraform, allow for the description of the desired state of the infrastructure without specifying the sequence of steps to achieve it. This approach ensures that the code always accurately represents the infrastructure's current state, enhancing clarity, reusability, and manageability.

Declarative languages: Terraform, Cloudformation, SaltStack, Puppet and OpenStack Heat

![Difference between procedural and declarative Approach](procedural-declarative.jpg "Difference between procedural and declarative Approach")

## CloudFormation

CloudFormation is a service provided by AWS that automates the provisioning and management of a wide range of AWS resources. It allows users to use programming languages or simple text files to model and provision, in an automated and secure manner, all the resources needed for their applications across all regions and accounts.

### Architecture Concepts
In advanced CloudFormation architecture, the focus is on designing scalable, resilient, and efficient infrastructure by leveraging the following concepts:

- **Templates**: CloudFormation templates are the blueprints for creating AWS resources. They define the resources to be created and the properties for those resources. Templates can include variables (Parameters), conditions, resource configurations, mappings, and outputs to create reusable infrastructure architectures.
- **Stacks**: The core unit of CloudFormation, stacks are collections of AWS resources that can be managed as a single unit. This means you can create, update, or delete a collection of resources by managing stacks. Stacks are created/deleted from a template
- **Change Sets**: Before updating a stack, change sets can be used to preview how the proposed changes might impact your running resources, allowing for a review process to ensure updates are as expected.
- **Drift Detection**: CloudFormation can detect drift on stack resources, which means it can identify configuration changes that deviate from the stack template, helping maintain consistency and compliance.

![Architecture CloudFormation](architecture-cloudformation.jpg "Architecture CloudFormation")

## CloudFormation StackSets & Nested Stacks

### StackSets
StackSets extend the functionality of CloudFormation stacks by enabling you to create, update, or delete stacks across multiple accounts and regions with a single operation. This is particularly useful for large-scale deployments where consistency and automation across accounts and regions are critical.

![Stack Set](stack-sets.jpg "Stack Set")

### Nested Stacks
Nested Stacks allow you to organize your CloudFormation templates into reusable, manageable components. A nested stack is a stack that you create within another stack by using the AWS::CloudFormation::Stack resource. This "modular" approach simplifies the management of greater systems by allowing you to build layers of abstraction.

![Nested Stack](nested-stack.jpg "Nested Stack")

## Understanding CloudFormation Template Syntax

CloudFormation templates can be written in JSON or YAML format. They consist of five main sections: Parameters, Mappings, Conditions, Resources, and Outputs.

- **Parameters**: Enable input of custom values to your template at runtime.
- **Mappings**: A static key-value pair that can be used to match keys to corresponding values.
- **Conditions**: Define conditions to control whether certain resources are created or whether properties are assigned specific values during stack creation or update.
- **Resources**: The core section of the template, specifying the AWS resources to be created or managed.
- **Outputs**: Define the output values that you can import into other stacks or return as results after the stack is created.

### JSON Format CloudFormation Template

```json
{
  "AWSTemplateFormatVersion": "2010-09-09", // Optional - Defines which CloudFormation Version is used
  "Description": "An example CloudFormation template.", // Optional
  "Metadata": { // Optional - Additional Infos about template, to document in a tagging matter.
    "Template": "BasicExample"
  },
  "Parameters": { // Optional
    "InstanceType": {
      "Description": "EC2 instance type",
      "Type": "String",
      "Default": "t2.micro"
    }
  },
  "Mappings": { // Optional
    "RegionMap": {
      "us-west-1": {"AMI": "ami-0abcdef1234567890"},
      "eu-central-1": {"AMI": "ami-1234567890abcdef0"}
    }
  },
  "Conditions": { // Optional
    "CreateProdResources": {
      "Fn::Equals": [{"Ref": "EnvType"}, "prod"]
    }
  },
  "Transform": { // Optional
    "Name": "AWS::Include",
    "Parameters": {
      "Location": "s3://my-bucket/my-transform-macro.yml"
    }
  },
  "Resources": { // Required - Main part of the template
    "MyEC2Instance": {
      "Type": "AWS::EC2::Instance",
      "Properties": {
        "InstanceType": {"Ref": "InstanceType"},
        "ImageId": {"Fn::FindInMap": ["RegionMap", {"Ref": "AWS::Region"}, "AMI"]}
      }
    }
  },
  "Outputs": { // Optional
    "InstanceId": {
      "Description": "The Instance ID",
      "Value": {"Ref": "MyEC2Instance"}
    }
  }
}
```

### YAML Format CloudFormation Template

```yaml
AWSTemplateFormatVersion: '2010-09-09' # Optional - Defines which CloudFormation Version is used
Description: An example CloudFormation template. # Optional
Metadata: # Optional - Additional Infos about template, to document in a tagging matter.
  Template: BasicExample
Parameters: # Optional
  InstanceType:
    Description: EC2 instance type
    Type: String
    Default: t2.micro
Mappings: # Optional
  RegionMap:
    us-west-1:
      AMI: ami-0abcdef1234567890
    eu-central-1:
      AMI: ami-1234567890abcdef0
Conditions: # Optional
  CreateProdResources:
    Fn::Equals:
      - Ref: EnvType
      - prod
Transform: # Optional
  Name: 'AWS::Include'
  Parameters:
    Location: 's3://my-bucket/my-transform-macro.yml'
Resources: # Required - Main part of the template
  MyEC2Instance:
    Type: 'AWS::EC2::Instance'
    Properties:
      InstanceType: !Ref InstanceType
      ImageId: !FindInMap [RegionMap, !Ref 'AWS::Region', AMI]
Outputs: # Optional
  InstanceId:
    Description: The Instance ID
    Value: !Ref MyEC2Instance
```

## AWS CDK (Cloud Development Kit)

### What is CDK?
The AWS Cloud Development Kit (CDK) is a development framework for defining AWS cloud infrastructure in software like coding manner and provisioning it through CloudFormation.

![AWS CDK](aws-cdk.jpg "AWS CDK")

### CDK Supports:
- TypeScript
- JavaScript
- Python
- Java
- C#/.Net
- Go

### Why CDK?
- **Compress Template-Code**: Generate CloudFormation templates with less code.
- **Logical Expressions**: Use if-statements, loops, and other logical expressions.
- **Modular Approach**: Object-oriented programming structure to model infrastructure.
- **High-Level Abstractions**: Simplify the definition of cloud resources.
- **Shareable & Reusable Code**: Create readable and reusable code libraries.
- **Testing**: Apply industry-standard protocols to test infrastructure code.
- **Code Reviews**: Improve code quality through reviews.
- **Language Independence**: Use familiar programming languages without needing to learn new ones.

### CDK Concepts:
- **Constructs**: Basic building blocks representing resources.
- **Apps**: Root construct initiating other constructs.
- **Stacks**: Unit of deployment within a specific scope.
- **Environments**: Target AWS account and region for deployment.
- **Identifiers & Tokens**: Unique identifiers and placeholders for resources.
- **Parameters & Tagging**: Deployment-time variables and resource management tags.
- **Assets**: Local files and Docker images for deployment.
- **Permissions**: Access and permission management through IAM.
- **Context & Feature Flags**: Key-value pairs for additional information and backward compatibility.
- **Aspects & Escape Hatches**: Operations on constructs and integration of unsupported features.
- **Bootstrapping**: Preparing a CDK environment with necessary resources.

## Terraform Overview

### Introduction to Terraform
Terraform is a powerful tool designed for building, changing, and versioning infrastructure safely and efficiently. As an open-source project initiated by HashiCorp in 2014, it has rapidly become a key player in the infrastructure as code (IaC) paradigm.

- **Infrastructure as Code (IaC)**: Terraform enables the management of infrastructure through code to automate the setup and maintenance of hardware components.
- **Open Source Project**: It is maintained as an open-source project, fostering a broad community of contributors and users.
- **Project Origin**: The project's development began in 2014, aiming to provide a universal tool for managing diverse cloud services. [Terraform on GitHub](https://github.com/hashicorp/terraform)

### Terraform's Capabilities
- **Virtual Server Lifecycle Management**: Supports a variety of providers such as AWS, VMware, Azure, and GCP, managing the lifecycle of virtual servers.
- **Supporting Services Management**: Capable of managing specific services such as DNS and email systems.
- **System Services Management**: Facilitates the management of system-level services like MySQL and PostgreSQL databases.

### Configuration and Design
- **Config Files**: Terraform uses HCL or JSON for its configuration files (.tf), offering a user-friendly syntax for declaring infrastructure components.
- **HashiCorp**: As a HashiCorp creation, Terraform joins a suite of tools like Vagrant, designed to enhance and simplify the management of development environments.
- **Direct API Use**: Unlike tools such as AWS CloudFormation, Terraform communicates directly with the provider's API, enabling more granular control and flexibility in managing resources across different cloud platforms.

### Top Level Keywords
- **provider**: Specifies a plugin that Terraform uses to interact with cloud providers, services, and other APIs. It defines the necessary information to connect to a service, like AWS or Google Cloud, such as credentials and region.

- **variable**: Variables in Terraform are placeholders for values that can be set at runtime. They allow for customization of Terraform configurations without altering the code.

- **resource**: A resource block defines a piece of infrastructure, like a virtual machine, network, or database. Terraform uses these definitions to create, manage, and update infrastructure components.

- **output**: Output values are like return values for a Terraform module. They can be used to extract information about the infrastructure, such as IPs, hostnames, and IDs, which can be used elsewhere or displayed to the user.

- **module**: Modules are containers for multiple resources that are used together. A module can be reused across different projects to create predefined sets of resources.

- **data**: Data sources allow Terraform to use information defined outside of Terraform, or defined by another separate Terraform configuration.

- **terraform**: A special block where you define Terraform settings, such as required Terraform version, backend configuration, etc.

- **locals**: Locals are named values that you can use to simplify or avoid repetition in your Terraform code. Unlike variables, locals are not user input but are more like constants within a module.

### example.tf
```terraform
    resource "aws_instance" "web" {
      ami           = "ami-0375ca3842950ade6"
      instance_type = "t2.micro"
    }

    resource "dnsimple_record" "web" {
      domain = "hashicorp.com"
      name   = "web"
      ttl    = "3600"
      type   = "A"
      value  = aws_instance.web.public_ip
    }
```

### Terraform's internal Structure
Core <-> Plugins <-> Upstream APIs

### Core Concepts
- **Config**: Target Reality
- **State**: Current Reality
- **Diff**:[Config - State]
- **Plan**: Presents Diff
- **Apply**: Resolves Diff

## Terraform CLI and some important commands
- All interactions with terraform occur via CLI
- TF is a local tool (runs on current machine)
- ecosystem with different providers of cloud services and module repo

- `terraform init` to initialize new working directory containing .tf config files
- `terraform fmt` for canonical formatting + reporting syntax errors

![Terraform Commands](terraform-commands.jpg "Terraform Commands")

### Terraform Deployment Lifecycle
![Terraform Deployment Lifecycle](tf-deployment-lifecycle.jpg "Terraform Deployment Lifecycle")

Mache mir eine sehr gute Zusammenfassung über "terraform plan" in english in MD (nur H3) aus den nachfolgenden Informationen. Bitte so kompakt, übersichtlich und prägnant wie möglich!

### Command: terraform plan
- The terraform plan command is used to create an execution plan. Terraform performs a refresh, unless explicitly disabled, and then determines what actions are necessary to achieve the desired state specified in the configuration files
- Computes the desired state of the configuration

#### Options
- **-destroy** - If set, generates a plan to destroy all the known resources.
- **-input=true** - Ask for input for variables if not directly set.
- **-out=path** - The path to save the generated execution plan. This plan can then be used with terraform apply to be certain that only the changes shown in this plan are applied.
- **-var 'foo=bar'** - Set a variable in the Terraform configuration

#### Diff symbols
- **+** resource will be created
- **-** resource will be deleted
- **~** resource will be updated in place
- **-/+** resource(s) will be destroyed and re-created
 
### Command: terraform apply
- The terraform apply command is used to apply the changes required to reach the desired state of the configuration, or the pre-determined set of actions generated by a terraform plan execution plan.
- Executes all differences between current state and configured state

#### Options
- **-input=true** - Ask for input for variables if not directly set
- **-var 'foo=bar'** - Set a variable in the Terraform configuration.
- **-auto-approve** - Apply plan without confirmation
- …

### Command: terraform show
- The terraform show command is used to provide human-readable output from a state or plan file.
- Inspect your infrastructure 

#### Options
- **-module-depth=n** - Specifies the depth of modules to show in the output.

### Command: terraform state
- The terraform state list command is used to list resources within a Terraform state. You state list without any options shows up all resources. In addition you have the possibility to filter by module or resource.
- Usage: terraform state list [options] [address…]

### Command: terraform destroy
The terraform destroy command is used to destroy the Terraform-managed infrastructure. 
This will ask for confirmation before destroying

Options: see terraform destroy --help

### Rollback via version control
Terraform only knows the configuration & state of your infrastructure. Use version control and revert to earlier version (of main.tf). Then run terraform apply on it.

### Common Terraform folder structure
![Common Terraform folder structure](tf-folder-structure.jpg "Common Terraform folder structure")

## State
Terraform stores the state of the infrastructure from the last time Terraform was run. The state is used to create plans and make changes to your infrastructure. It is critical that this state is maintained appropriately so future runs operate as expected. It's important to note that TF state files can contain sensitive data. Therefore it's recommended to not store the TF state in source control.

- State: Awarness of what is deployed and what is configured
- Maps resources to config, keep track of metadata
- Local state: stored in terraform.tfstate
- backup of previous state lives in terraform.tfstate.backup

Terraform stores its state locally in terraform.tfstate (not encrypted) by default, but for team collaboration, it allows to store the state remotly for example in Amazon S3, TF Cloud etc. to ensure consistency. Remote state encryption is backend-specific!

## Meta-Arguments

- **Meta-Arguments**: Control Terraform's behavior, not directly linked to cloud resources.

- **count**: Define the number of identical resources to create without loops.

- **depends_on**: Explicitly set dependencies for resource creation order.

- **provider**: Specify which provider to use for a resource, useful in multi-provider setups.

- **lifecycle**: Manage resource lifecycle rules, like prevention of destruction.

## Providers in Terraform

- **Role**: Interact with APIs, expose resources.
- **Types**: IaaS (e.g., AWS), PaaS (e.g., Heroku), SaaS (e.g., Terraform Enterprise).

### Provider for AWS
**Access**: Requires AWS account details.
**Interaction**: Defines how Terraform interacts with AWS API.
**Configuration**:
  - Minimal: `provider "aws" {}`
  - Detailed:
    ```hcl
        provider "aws" { 
          region = "us-west-2" 
          access_key = "anaccesskey" 
          secret_key = "asecretkey" 
        }
    ```
**Credentials**:
  - Set via environment variables, not in `providers.tf`.
  - Use a shared credentials file or assume a role for security.

### Best Practices
**File Structure**: Define all providers in `providers.tf`.
**Security**: Never hardcode access keys; use environment variables or config files.
**Aliases**: Use aliases for handling multiple provider instances.
  - Default provider has no alias.
  - Additional providers require an alias.
**Explicit Use**: Resources can specify which provider to use with the `provider` setting.

### Example with Alias & Versioning
```hcl
    provider "aws" {
      version = ">= 1.19.0"
      alias = "providerAlias"
      region = "${var.region}" 
    }
    resource "aws_vpn_gateway" "vpn_gw" { 
      provider = "aws.providerAlias"
      vpc_id = "vpc_123456gw"  
    }
```

## Variables in Terraform
- Variables in Terraform resemble those in programming languages.
- They replace hardcoded values with flexible parameters in configurations.
- Variables enhance clarity and reusability of configurations.
- Every variable must be assigned a value; none are optional, though default values can be set.

Types: Most common types are strings, numbers, lists and maps. Other accepted types are booleans, sets, objects and tuples. If omitted, the type is inferred from the default value. If the type and the default value is missing, it's assumed to be a string.

```hcl
    # Variable declaration with string type
    variable "image_id" {
      type = string
    }

    # Variable with a default list value
    variable "availability_zone_names" {
      type    = list(string)
      default = ["us-west-1a"]
    }

    # Variable declaration for a map
    variable "tags" {
      type = map(string)
    }

    # Usage of string interpolation
    resource "aws_instance" "example" {
      ami           = var.image_id
      instance_type = "t2.micro"

      # Interpolate variable into a string
      tags = {
        Name = "Server-${var.image_id}"
      }
    }

    # Multiline string with heredoc syntax
    resource "aws_security_group" "example" {
      name = "security_group_name"
      description = <<EOF
    This is a multiline description
    that spans several lines
    using heredoc syntax.
    EOF
    }

    # Numeric values, including hex
    resource "aws_ebs_volume" "example" {
      size = 10 # base 10 integer
      # Hexadecimal value for the number of IOPS
      iops = 0x100 
    }

    # Boolean value
    resource "aws_instance" "example_with_condition" {
      ami           = var.image_id
      instance_type = "t2.micro"
      monitoring    = true # Boolean value
    }

    # List value
    resource "aws_autoscaling_group" "example" {
      availability_zones = var.availability_zone_names
      min_size           = 1
      max_size           = 5
    }

    # Map value
    resource "aws_instance" "example_with_tags" {
      ami           = var.image_id
      instance_type = "t2.micro"

      # Map variable usage
      tags = var.tags
    }

    # Conditional expression
    resource "aws_elb" "example" {
      name               = "foobar-terraform-elb"
      availability_zones = var.availability_zone_names

      # Conditional example - if instance is production, use 5 instances, else use 1
      instances = var.environment == "production" ? [aws_instance.production.*.id] : [aws_instance.development.id]
    }
```

{{% callout warning %}}
Never put secret values, like passwords or access tokens in .tf files or other files that are checked into source control!
{{% /callout %}}

## Locals in Terraform
In Terraform, `locals` are used to simplify and reuse expressions within a module. Think of it as a local variable within a function in Python that can only be addressed within the function.

Example:

```hcl
    locals {
      # Define a local value
      service_name = "my-service"
    }

    resource "aws_s3_bucket" "example" {
      # Use the local value
      bucket = "${local.service_name}-data"
    }
```

## Terraform Resource Configuration

### AWS Provider and Resources

The AWS provider facilitates interactions with the many resources supported by AWS. Resources are defined as follows:

```hcl
    resource "TYPE" "NAME" {
      CONFIG ...
      [for_each = FOR_EACH]
      [count = COUNT]
      [depends_on = [NAME, ...]]
      [provider = PROVIDER]
    }
```

### Resource Configuration Example

A basic resource configuration for an AWS instance might look like this:

```hcl
    resource "aws_instance" "example" {
      ami           = "ami-275f631"
      instance_type = "t2.micro"
    }
```

### Using `for_each` and `count`

`for_each` and `count` are used to create multiple instances of a resource:

- `for_each` is used to iterate over a map or set of values, creating one resource per item.
- `count` is used to create a specified number of instances of a resource.

Examples:

```hcl
    # for_each
    resource "aws_subnet" "public_subnet" {
      for_each = var.subnet_numbers
      # Additional configurations ...
    }

    # count
    resource "aws_subnet" "public_subnet" {
      count = 4
      # Additional configurations ...
    }
```

### Lifecycle and Timeouts

Lifecycle policies and timeouts can be configured to control resource behavior on changes:

- `lifecycle` can be used to ignore certain changes or prevent resource destruction.
- `timeouts` define how long Terraform should wait for a resource to be created or deleted.

```hcl
    resource "aws_instance" "example" {
      # Configurations ...
      lifecycle {
        ignore_changes = [ami]
        prevent_destroy = true
      }

      timeouts {
        create = "60m"
        delete = "2h"
      }
    }
```

### Best Practices

- Create a file for a bundle of resources that belong together.
- Use modules instead of a complex file structure as the infrastructure grows.

```hcl
    # Example for a resource file
    module "my_module" {
      source = "./modules/my_module"
      # Additional configurations ...
    }
```

## Terraform Provisioners

### Definition and Usage

Provisioners in Terraform are used to execute scripts on a local or remote machine as part of resource creation or destruction.

```hcl
    resource "aws_instance" "example" {
      ami           = "ami-275f631"
      instance_type = "t2.micro"

      provisioner "local-exec" {
        command = "echo ${aws_instance.example.private_ip} >> inventory.txt"
      }
    }
```

### Types of Provisioners

- **Creation-Time Provisioners**: These are run only during the creation of the resource, not during updating or any other lifecycle event. They are designed for initial resource setup.
- **Destroy-Time Provisioners**: These run when the resource is being destroyed, if specified with `when = "destroy"`.

### Provisioning Best Practices

- **Good**: Automating the creation of infrastructure and instance initialization with `user_data` or AWS `cloud-init`.
- **Better**: Using `remote-exec` provisioner on a base AMI to run a few commands upon instance creation.
- **Best**: Building AMIs with Packer to ensure minimal configuration is needed during provisioning.

## Terraform Data Sources and Outputs

### Data Sources

Data sources in Terraform are used to fetch or compute data for use elsewhere in your Terraform configuration. They allow a Terraform configuration to build on information defined outside of Terraform or defined by another separate Terraform configuration. For most AWS Resources, there is an equivalent Data Source available for querying data.

Example of a Data Source configuration:

```hcl
    data "aws_ami" "web" {
      filter {
        name   = "state"
        values = ["available"]
      }

      filter {
        name   = "tag:Component"
        values = ["web"]
      }

      most_recent = true
    }

    cluster_id = data.terraform_remote_state.base.iac_ecs_cluster.ecs_cluster_id
```

### Outputs

Outputs in Terraform are used to output important data from your Terraform configuration that you want to easily access or use in other configurations. This data can be outputted when Terraform apply is called and can be queried using the Terraform output command.

Outputs are particularly useful for displaying computed values like IP addresses, DNS names, and resource IDs. They can be consumed by other Terraform configurations or modules.

Example of defining an output:

```hcl
    output "public_ip" {
      value = aws_instance.web.public_ip
    }

    output "public_dns" {
      value = aws_instance.web.public_dns
    }
```

Example of querying an output:

```shell
    > terraform output
    public_dns = ec2-34-222-156-11.us-west-2.compute.amazonaws.com
    public_ip = 34.222.156.11
```

## Backends in Terraform
Backends in Terraform are configuration elements that determine where and how the infrastructure state is stored, crucial for collaboration in teams and managing remote operations.

### Functions of a Backend:
- **State Storage:** Backends allow storing the state in a remote environment like AWS S3 instead of locally on the disk. This promotes collaboration as the team can access the same state.
  
- **Locking Mechanism:** To prevent state corruption, some backends, such as Terraform Cloud or Enterprise, offer locking mechanisms that block concurrent state modifications.

- **Sensitive Information:** By using backends like S3, sensitive information is not stored on the local disk, enhancing security.

- **Remote Operations:** For large infrastructures or specific changes, `terraform apply` operations can take a long time. Backends enable these operations to be executed remotely, allowing you to turn off your computer in the meantime.

### Initialization:
The `terraform init` command must be called whenever a new environment is set up or any change to the backend configuration is made, to initialize or update the backend.

### Configuration:
A backend's configuration is done directly in Terraform files within the `terraform` block.

Example of S3 backend configuration:

```hcl
    terraform {
      backend "s3" {
        bucket = "mybucket"
        key    = "path/to/my/key"
        region = "us-east-1"
      }
    }
```

In this example, the S3 backend is configured to store the Terraform state in a specified S3 bucket. The path to the state key and the bucket's region are specified. This configuration allows multiple users to manage the state consistently and carry out operations securely and efficiently.

## Terraform Modules Overview

### Initial Setup with Modules

- Start with everything in `main.tf`.
- Basic AWS provider configuration and a VPC resource with output:

```hcl
    provider "aws" {
      region = "eu-west-1"
    }

    resource "aws_vpc" "this" {
      cidr_block           = "10.10.0.0/16"
      enable_dns_hostnames = true
    }

    output "this_vpc_id" {
      value = "${aws_vpc.this.id}"
    }
```

### When to Use Modules

As the project grows (20+ resources and data sources), issues arise:
  - Increasing code size.
  - Complicated dependencies between resources.
  - Large impact on `terraform apply`.

Modules solve these issues by organizing Terraform configurations into folders.

### Types of Modules

**Resource modules** (`terraform-aws-modules`), used for:
  - Creating resources.
  - Minimal inter-module dependencies.
  - High flexibility.

**Infrastructure modules** incorporate:
  - Specific versions of resource modules.
  - Company-wide standards (e.g., tagging conventions).

### Module Implementation Example

**Resource Module Example**:

```hcl
    module "atlantis_alb_sg" {
      source  = "terraform-aws-modules/security-group/aws//modules/https-443"
      version = "v2.0.0"

      name        = "atlantis-alb"
      vpc_id      = "vpc-12345678"
      description = "Security group with HTTPS ports open for everybody (IPv4 CIDR)"
      ingress_cidr_blocks = ["0.0.0.0/0"]
    }
```

**Infrastructure Module Example**:

```hcl
    module "atlantis" {
      source = "terraform-aws-modules/atlantis/aws"

      name   = "atlantis"
      # VPC
      cidr            = "10.20.0.0/20"
      azs             = ["eu-west-1a", "eu-west-1b", "eu-west-1c"]
      private_subnets = ["10.20.1.0/24", "10.20.2.0/24", "10.20.3.0/24"]
      public_subnets  = ["10.20.101.0/24", "10.20.102.0/24", "10.20.103.0/24"]
      # DNS
      route53_zone_name = "terraform-aws-modules.modules.tf"
      # Atlantis app
      atlantis_github_user       = "atlantis-bot"
      atlantis_github_user_token = "examplegithubtoken"
    }
```

### Organizing Modules

Categorize by function:
  - **Front-end Services**: Websites, mobile back-end.
  - **Back-end Services**: Search, payments, reviews.
  - **Shared Services**: CRM databases, monitoring.
  - **Base Network**: VPCs, IGWs, VPNs, NATs.
  - **Identity**: IAM policies, users, groups.

### Tips and Best Practices

Utilize the **Terraform Module Registry** for discovering and using community modules.
- Good Terraform modules have:
  - Clean code.
  - Rich features.
  - Sensible defaults.
  - Tests, examples, documentation.
  - Security, versioning, lifecycle-readiness.

### Module References Storage
`.terraform` directory stores module references, allowing immediate access to module changes. Use `tree` or `ls -1` to view the `.terraform` directory contents for modules and plugins.

## Terraform Troubleshooting

### Potential Issues

Mismanagement of resources in the cloud can lead to critical issues:
- Accidental deletion of resources.
- Unauthorized addition of critical resources.
- Configuration drift from the intended state.

### Commands for Troubleshooting

Terraform provides a series of commands to help manage and troubleshoot resources:

#### Listing Current State
To see the current state of resources as known by Terraform:

```shell
    terraform state list
```

#### Detecting Configuration Drift
To actively query the current state of the resources and detect any changes:

```shell
    terraform plan
```

#### Applying Corrections
To apply the necessary changes to reach the desired state configuration:

```shell
    terraform apply
```

#### Importing Resources
If a resource exists in the cloud but not in Terraform's state, it can be imported:

```shell
    terraform import <ADDRESS> <ID>
```

For example, to import an AWS instance:

```shell
    terraform import aws_instance.example i-abcd1234
```

#### Reconciling State
The `terraform refresh` command updates the state file with the real-world infrastructure:

```shell
    terraform refresh
```

This is useful for ensuring that Terraform's state matches the actual infrastructure and for detecting drift. 

The `terraform state list` command will then list the updated resources known to the state file.