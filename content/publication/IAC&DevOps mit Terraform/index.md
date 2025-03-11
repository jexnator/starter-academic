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
  caption: "Image credit: [**Adobe Stock: ArtemisDiana**](https://adobe.ly/3KWGRwp)"
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

# {{< highlight go >}}<b>DevOps and Automation Module</b>{{< /highlight >}}<br>

## {{< highlight go >}}<b>Introduction to DevOps</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>What is DevOps?</b>{{< /highlight >}}<br>

DevOps merges cultural philosophies, practices, and tools to enhance an organization's ability to deliver applications and services at high velocity, outpacing organizations with traditional development and infrastructure management processes. This synergy of development and operations aims for a continuous delivery model emphasizing repeatability, reliability, stability, resilience, and security, alongside operational efficiency improvements.

![DevOps](devops.jpg "DevOps")

#### {{< highlight go >}}<b>DevOps Culture</b>{{< /highlight >}}<br>

The essence of DevOps culture lies in eliminating the barriers between development and operations teams, fostering an environment where both work in unison to amplify productivity and operational reliability. The movement's core values are encapsulated in the mantra "People over Process over Tools" and include:

- Culture
- Automation
- Measurement
- Sharing

These values guide the practical benefits of DevOps principles, allowing for frequent code deployments and the creation of resilient, self-healing systems equipped with advanced monitoring and alerting capabilities.

### {{< highlight go >}}<b>Benefits of DevOps and AWS Tooling</b>{{< /highlight >}}<br>

DevOps practices enable organizations to deploy code multiple times a day, significantly reducing outages and downtime through the use of resilient systems. AWS services further enhance DevOps practices by providing tools that support continuous integration and delivery, infrastructure automation, and a consistent approach across projects.

![DevOps Tooling by AWS](devops-tooling-aws.jpg "DevOps Tooling by AWS")

#### {{< highlight go >}}<b>Continuous Integration and Delivery Pipeline</b>{{< /highlight >}}<br>

Key components include:

- **Continuous Integration (CI):** Regularly merging code changes into a central repository to run automated builds and tests.
- **Automation:** Minimizing risks associated with manual processes by automating infrastructure management, which is achieved through Infrastructure as Code (IaC) and layered architecture designs.

![Components DevOps](components-devops.jpg "Components of DevOps Practise")

## {{< highlight go >}}<b>Infrastructure as Code (IaC) Overview</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Understanding IaC</b>{{< /highlight >}}<br>

Infrastructure as Code is a paradigm that manages and provisions infrastructure through code rather than manual processes, promoting reliability, reproducibility, and documentation. IaC tools range from ad hoc scripts for single-use tasks to configuration management tools like Chef, Puppet, Ansible, and SaltStack, which automate software installation on servers.

Below is an overview of the different types of tools used in IaC.

### {{< highlight go >}}<b>Ad Hoc Scripts</b>{{< /highlight >}}<br>

Ad hoc scripts are simple, often improvised commands or sets of commands that are used to perform a specific task on one or more servers. They are the most basic form of automation, providing a quick and easy way to get things done without the need for more complex tooling. However, they can become difficult to manage and scale as infrastructure grows and changes.

![Ad Hoc Scripts](ad-hoc-scripts.jpg "Ad Hoc Scripts")

### {{< highlight go >}}<b>Configuration Management Tools</b>{{< /highlight >}}<br>

Configuration management tools automate the process of controlling and tracking changes in the software, and ensuring that it is consistent and maintains its integrity over time. They can install and manage software on existing servers, enforce desired states, and automate routine tasks.

![Configuration Management Tools](conf-manage-tools.jpg "Configuration Management Tools")

#### {{< highlight go >}}<b>Examples of Configuration Management Tools:</b>{{< /highlight >}}<br>

- **Chef**: A powerful automation platform that transforms infrastructure into code, allowing servers to be automatically set up and managed across a network.
- **Puppet**: Puppet manages infrastructure as code, automating the configuration and management of machines and the software running on them.
- **Ansible**: A simple, yet powerful, server and configuration management tool with a focus on simplicity and ease of use. It uses playbooks to describe automation jobs, and SSH for communication with servers.
- **SaltStack**: SaltStack is designed for IT automation, system and configuration management, and orchestrating complex software-defined data center environments.

### {{< highlight go >}}<b>Server Templating Tools</b>{{< /highlight >}}<br>

Server templating tools are used to create images of server configurations, which can be rapidly deployed. This allows for the creation of consistent, repeatable server setups that can be quickly spun up or down as needed.

![Server Templating Tools](server-templating.jpg "Server Templating Tools")

#### {{< highlight go >}}<b>Examples of Server Templating Tools:</b>{{< /highlight >}}<br>

- **Docker**: Docker packages software into standardized units called containers that have everything the software needs to run including libraries, system tools, code, and runtime.
- **Packer**: Packer automates the creation of any type of machine image. It embraces modern configuration management by encouraging you to use automated scripts to install and configure the software within your Packer-made images.
- **Vagrant**: Vagrant provides easy to configure, reproducible, and portable work environments built on top of industry-standard technology and controlled by a single consistent workflow to help maximize productivity and flexibility.

### {{< highlight go >}}<b>Server Provisioning Tools</b>{{< /highlight >}}<br>

Server provisioning tools are responsible for the initial setup of servers. They can create servers, install operating systems, and then hand them off to configuration management tools for further setup.

![Server Provisioning Tools](server-provisioning-tools.jpg "Server Provisioning Tools")

#### {{< highlight go >}}<b>Examples of Server Provisioning Tools:</b>{{< /highlight >}}<br>

- **Terraform**: Terraform is an open-source infrastructure as code software tool created by HashiCorp. It enables users to define and provision a data center infrastructure using a declarative configuration language.
- **CloudFormation**: AWS CloudFormation provides a common language for you to model and provision AWS and third-party application resources in your cloud environment.

### {{< highlight go >}}<b>Procedural Language vs. Declarative Language Definition</b>{{< /highlight >}}<br>

Procedural languages are characterized by their focus on the sequence of operations to perform a task. They do not inherently capture the complete state of the infrastructure, making it difficult to understand the deployment's current state without knowing the order in which scripts or templates were executed. This sequential nature also limits the reusability of procedural code, as adjustments must often be made based on the infrastructure's existing state.

Procedural languages: Chef & Ansible

In contrast, declarative languages, as used in tools like CloudFormation and Terraform, allow for the description of the desired state of the infrastructure without specifying the sequence of steps to achieve it. This approach ensures that the code always accurately represents the infrastructure's current state, enhancing clarity, reusability, and manageability.

Declarative languages: Terraform, Cloudformation, SaltStack, Puppet and OpenStack Heat

![Difference between procedural and declarative Approach](procedural-declarative.jpg "Difference between procedural and declarative Approach")

## {{< highlight go >}}<b>CloudFormation</b>{{< /highlight >}}<br>

CloudFormation is a service provided by AWS that automates the provisioning and management of a wide range of AWS resources. It allows users to use programming languages or simple text files to model and provision, in an automated and secure manner, all the resources needed for their applications across all regions and accounts.

### {{< highlight go >}}<b>Architecture Concepts</b>{{< /highlight >}}<br>

In advanced CloudFormation architecture, the focus is on designing scalable, resilient, and efficient infrastructure by leveraging the following concepts:

- **Templates**: CloudFormation templates are the blueprints for creating AWS resources. They define the resources to be created and the properties for those resources. Templates can include variables (Parameters), conditions, resource configurations, mappings, and outputs to create reusable infrastructure architectures.
- **Stacks**: The core unit of CloudFormation, stacks are collections of AWS resources that can be managed as a single unit. This means you can create, update, or delete a collection of resources by managing stacks. Stacks are created/deleted from a template
- **Change Sets**: Before updating a stack, change sets can be used to preview how the proposed changes might impact your running resources, allowing for a review process to ensure updates are as expected.
- **Drift Detection**: CloudFormation can detect drift on stack resources, which means it can identify configuration changes that deviate from the stack template, helping maintain consistency and compliance.

![Architecture CloudFormation](architecture-cloudformation.jpg "Architecture CloudFormation")

## {{< highlight go >}}<b>CloudFormation StackSets & Nested Stacks</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>StackSets</b>{{< /highlight >}}<br>

StackSets extend the functionality of CloudFormation stacks by enabling you to create, update, or delete stacks across multiple accounts and regions with a single operation. This is particularly useful for large-scale deployments where consistency and automation across accounts and regions are critical.

![Stack Set](stack-sets.jpg "Stack Set")

### {{< highlight go >}}<b>Nested Stacks</b>{{< /highlight >}}<br>

Nested Stacks allow you to organize your CloudFormation templates into reusable, manageable components. A nested stack is a stack that you create within another stack by using the AWS::CloudFormation::Stack resource. This "modular" approach simplifies the management of greater systems by allowing you to build layers of abstraction.

![Nested Stack](nested-stack.jpg "Nested Stack")

## {{< highlight go >}}<b>Understanding CloudFormation Template Syntax</b>{{< /highlight >}}<br>

CloudFormation templates can be written in JSON or YAML format. They consist of five main sections: Parameters, Mappings, Conditions, Resources, and Outputs.

- **Parameters**: Enable input of custom values to your template at runtime.
- **Mappings**: A static key-value pair that can be used to match keys to corresponding values.
- **Conditions**: Define conditions to control whether certain resources are created or whether properties are assigned specific values during stack creation or update.
- **Resources**: The core section of the template, specifying the AWS resources to be created or managed.
- **Outputs**: Define the output values that you can import into other stacks or return as results after the stack is created.

### {{< highlight go >}}<b>JSON Format CloudFormation Template</b>{{< /highlight >}}<br>

```json
{
  "AWSTemplateFormatVersion": "2010-09-09", // Optional - Defines which CloudFormation Version is used
  "Description": "An example CloudFormation template.", // Optional
  "Metadata": {
    // Optional - Additional Infos about template, to document in a tagging matter.
    "Template": "BasicExample"
  },
  "Parameters": {
    // Optional
    "InstanceType": {
      "Description": "EC2 instance type",
      "Type": "String",
      "Default": "t2.micro"
    }
  },
  "Mappings": {
    // Optional
    "RegionMap": {
      "us-west-1": { "AMI": "ami-0abcdef1234567890" },
      "eu-central-1": { "AMI": "ami-1234567890abcdef0" }
    }
  },
  "Conditions": {
    // Optional
    "CreateProdResources": {
      "Fn::Equals": [{ "Ref": "EnvType" }, "prod"]
    }
  },
  "Transform": {
    // Optional
    "Name": "AWS::Include",
    "Parameters": {
      "Location": "s3://my-bucket/my-transform-macro.yml"
    }
  },
  "Resources": {
    // Required - Main part of the template
    "MyEC2Instance": {
      "Type": "AWS::EC2::Instance",
      "Properties": {
        "InstanceType": { "Ref": "InstanceType" },
        "ImageId": {
          "Fn::FindInMap": ["RegionMap", { "Ref": "AWS::Region" }, "AMI"]
        }
      }
    }
  },
  "Outputs": {
    // Optional
    "InstanceId": {
      "Description": "The Instance ID",
      "Value": { "Ref": "MyEC2Instance" }
    }
  }
}
```

### {{< highlight go >}}<b>YAML Format CloudFormation Template</b>{{< /highlight >}}<br>

```yaml
AWSTemplateFormatVersion: "2010-09-09" # Optional - Defines which CloudFormation Version is used
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
  Name: "AWS::Include"
  Parameters:
    Location: "s3://my-bucket/my-transform-macro.yml"
Resources: # Required - Main part of the template
  MyEC2Instance:
    Type: "AWS::EC2::Instance"
    Properties:
      InstanceType: !Ref InstanceType
      ImageId: !FindInMap [RegionMap, !Ref "AWS::Region", AMI]
Outputs: # Optional
  InstanceId:
    Description: The Instance ID
    Value: !Ref MyEC2Instance
```

## {{< highlight go >}}<b>AWS CDK (Cloud Development Kit)</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>What is CDK?</b>{{< /highlight >}}<br>

The AWS Cloud Development Kit (CDK) is a development framework for defining AWS cloud infrastructure in software like coding manner and provisioning it through CloudFormation.

![AWS CDK](aws-cdk.jpg "AWS CDK")

### {{< highlight go >}}<b>CDK Supports:</b>{{< /highlight >}}<br>

- TypeScript
- JavaScript
- Python
- Java
- C#/.Net
- Go

### {{< highlight go >}}<b>Why CDK?</b>{{< /highlight >}}<br>

- **Compress Template-Code**: Generate CloudFormation templates with less code.
- **Logical Expressions**: Use if-statements, loops, and other logical expressions.
- **Modular Approach**: Object-oriented programming structure to model infrastructure.
- **High-Level Abstractions**: Simplify the definition of cloud resources.
- **Shareable & Reusable Code**: Create readable and reusable code libraries.
- **Testing**: Apply industry-standard protocols to test infrastructure code.
- **Code Reviews**: Improve code quality through reviews.
- **Language Independence**: Use familiar programming languages without needing to learn new ones.

### {{< highlight go >}}<b>CDK Concepts:</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Terraform Overview</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Introduction to Terraform</b>{{< /highlight >}}<br>

Terraform is a powerful tool designed for building, changing, and versioning infrastructure safely and efficiently. As an open-source project initiated by HashiCorp in 2014, it has rapidly become a key player in the infrastructure as code (IaC) paradigm.

- **Infrastructure as Code (IaC)**: Terraform enables the management of infrastructure through code to automate the setup and maintenance of hardware components.
- **Open Source Project**: It is maintained as an open-source project, fostering a broad community of contributors and users.
- **Project Origin**: The project's development began in 2014, aiming to provide a universal tool for managing diverse cloud services. [Terraform on GitHub](https://github.com/hashicorp/terraform)

### {{< highlight go >}}<b>Terraform's Capabilities</b>{{< /highlight >}}<br>

- **Virtual Server Lifecycle Management**: Supports a variety of providers such as AWS, VMware, Azure, and GCP, managing the lifecycle of virtual servers.
- **Supporting Services Management**: Capable of managing specific services such as DNS and email systems.
- **System Services Management**: Facilitates the management of system-level services like MySQL and PostgreSQL databases.

### {{< highlight go >}}<b>Configuration and Design</b>{{< /highlight >}}<br>

- **Config Files**: Terraform uses HCL or JSON for its configuration files (.tf), offering a user-friendly syntax for declaring infrastructure components.
- **HashiCorp**: As a HashiCorp creation, Terraform joins a suite of tools like Vagrant, designed to enhance and simplify the management of development environments.
- **Direct API Use**: Unlike tools such as AWS CloudFormation, Terraform communicates directly with the provider's API, enabling more granular control and flexibility in managing resources across different cloud platforms.

### {{< highlight go >}}<b>Top Level Keywords</b>{{< /highlight >}}<br>

- **provider**: Specifies a plugin that Terraform uses to interact with cloud providers, services, and other APIs. It defines the necessary information to connect to a service, like AWS or Google Cloud, such as credentials and region.

- **variable**: Variables in Terraform are placeholders for values that can be set at runtime. They allow for customization of Terraform configurations without altering the code.

- **resource**: A resource block defines a piece of infrastructure, like a virtual machine, network, or database. Terraform uses these definitions to create, manage, and update infrastructure components.

- **output**: Output values are like return values for a Terraform module. They can be used to extract information about the infrastructure, such as IPs, hostnames, and IDs, which can be used elsewhere or displayed to the user.

- **module**: Modules are containers for multiple resources that are used together. A module can be reused across different projects to create predefined sets of resources.

- **data**: Data sources allow Terraform to use information defined outside of Terraform, or defined by another separate Terraform configuration.

- **terraform**: A special block where you define Terraform settings, such as required Terraform version, backend configuration, etc.

- **locals**: Locals are named values that you can use to simplify or avoid repetition in your Terraform code. Unlike variables, locals are not user input but are more like constants within a module.

### {{< highlight go >}}<b>example.tf</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Terraform's internal Structure</b>{{< /highlight >}}<br>

Core <-> Plugins <-> Upstream APIs

### {{< highlight go >}}<b>Core Concepts</b>{{< /highlight >}}<br>

- **Config**: Target Reality
- **State**: Current Reality
- **Diff**:[Config - State]
- **Plan**: Presents Diff
- **Apply**: Resolves Diff

## {{< highlight go >}}<b>Terraform CLI and some important commands</b>{{< /highlight >}}<br>

- All interactions with terraform occur via CLI
- TF is a local tool (runs on current machine)
- ecosystem with different providers of cloud services and module repo

- `terraform init` to initialize new working directory containing .tf config files
- `terraform fmt` for canonical formatting + reporting syntax errors

![Terraform Commands](terraform-commands.jpg "Terraform Commands")

### {{< highlight go >}}<b>Terraform Deployment Lifecycle</b>{{< /highlight >}}<br>

![Terraform Deployment Lifecycle](tf-deployment-lifecycle.jpg "Terraform Deployment Lifecycle")

### {{< highlight go >}}<b>Command: terraform plan</b>{{< /highlight >}}<br>

- The terraform plan command is used to create an execution plan. Terraform performs a refresh, unless explicitly disabled, and then determines what actions are necessary to achieve the desired state specified in the configuration files
- Computes the desired state of the configuration

#### {{< highlight go >}}<b>Options</b>{{< /highlight >}}<br>

- **-destroy** - If set, generates a plan to destroy all the known resources.
- **-input=true** - Ask for input for variables if not directly set.
- **-out=path** - The path to save the generated execution plan. This plan can then be used with terraform apply to be certain that only the changes shown in this plan are applied.
- **-var 'foo=bar'** - Set a variable in the Terraform configuration

#### {{< highlight go >}}<b>Diff symbols</b>{{< /highlight >}}<br>

- **+** resource will be created
- **-** resource will be deleted
- **~** resource will be updated in place
- **-/+** resource(s) will be destroyed and re-created

### {{< highlight go >}}<b>Command: terraform apply</b>{{< /highlight >}}<br>

- The terraform apply command is used to apply the changes required to reach the desired state of the configuration, or the pre-determined set of actions generated by a terraform plan execution plan.
- Executes all differences between current state and configured state

#### {{< highlight go >}}<b>Options</b>{{< /highlight >}}<br>

- **-input=true** - Ask for input for variables if not directly set
- **-var 'foo=bar'** - Set a variable in the Terraform configuration.
- **-auto-approve** - Apply plan without confirmation
- …

### {{< highlight go >}}<b>Command: terraform show</b>{{< /highlight >}}<br>

- The terraform show command is used to provide human-readable output from a state or plan file.
- Inspect your infrastructure

#### {{< highlight go >}}<b>Options</b>{{< /highlight >}}<br>

- **-module-depth=n** - Specifies the depth of modules to show in the output.

### {{< highlight go >}}<b>Command: terraform state</b>{{< /highlight >}}<br>

- The terraform state list command is used to list resources within a Terraform state. You state list without any options shows up all resources. In addition you have the possibility to filter by module or resource.
- Usage: terraform state list [options] [address…]

### {{< highlight go >}}<b>Command: terraform destroy</b>{{< /highlight >}}<br>

The terraform destroy command is used to destroy the Terraform-managed infrastructure.
This will ask for confirmation before destroying

Options: see terraform destroy --help

### {{< highlight go >}}<b>Rollback via version control</b>{{< /highlight >}}<br>

Terraform only knows the configuration & state of your infrastructure. Use version control and revert to earlier version (of main.tf). Then run terraform apply on it.

### {{< highlight go >}}<b>Common Terraform folder structure</b>{{< /highlight >}}<br>

![Common Terraform folder structure](tf-folder-structure.jpg "Common Terraform folder structure")

## {{< highlight go >}}<b>State</b>{{< /highlight >}}<br>

Terraform stores the state of the infrastructure from the last time Terraform was run. The state is used to create plans and make changes to your infrastructure. It is critical that this state is maintained appropriately so future runs operate as expected. It's important to note that TF state files can contain sensitive data. Therefore it's recommended to not store the TF state in source control.

- State: Awarness of what is deployed and what is configured
- Maps resources to config, keep track of metadata
- Local state: stored in terraform.tfstate
- backup of previous state lives in terraform.tfstate.backup

Terraform stores its state locally in terraform.tfstate (not encrypted) by default, but for team collaboration, it allows to store the state remotly for example in Amazon S3, TF Cloud etc. to ensure consistency. Remote state encryption is backend-specific!

## {{< highlight go >}}<b>Meta-Arguments</b>{{< /highlight >}}<br>

- **Meta-Arguments**: Control Terraform's behavior, not directly linked to cloud resources.

- **count**: Define the number of identical resources to create without loops.

- **depends_on**: Explicitly set dependencies for resource creation order.

- **provider**: Specify which provider to use for a resource, useful in multi-provider setups.

- **lifecycle**: Manage resource lifecycle rules, like prevention of destruction.

## {{< highlight go >}}<b>Providers in Terraform</b>{{< /highlight >}}<br>

- **Role**: Interact with APIs, expose resources.
- **Types**: IaaS (e.g., AWS), PaaS (e.g., Heroku), SaaS (e.g., Terraform Enterprise).

### {{< highlight go >}}<b>Provider for AWS</b>{{< /highlight >}}<br>

**Access**: Requires AWS account details.
**Interaction**: Defines how Terraform interacts with AWS API.
**Configuration**:

- Minimal: `provider "aws" {}`
- Detailed:
  `hcl
    provider "aws" { 
      region = "us-west-2" 
      access_key = "anaccesskey" 
      secret_key = "asecretkey" 
    }
`
  **Credentials**:
- Set via environment variables, not in `providers.tf`.
- Use a shared credentials file or assume a role for security.

### {{< highlight go >}}<b>Best Practices</b>{{< /highlight >}}<br>

**File Structure**: Define all providers in `providers.tf`.
**Security**: Never hardcode access keys; use environment variables or config files.
**Aliases**: Use aliases for handling multiple provider instances.

- Default provider has no alias.
- Additional providers require an alias.
  **Explicit Use**: Resources can specify which provider to use with the `provider` setting.

### {{< highlight go >}}<b>Example with Alias & Versioning</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Variables in Terraform</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Locals in Terraform</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Terraform Resource Configuration</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>AWS Provider and Resources</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Resource Configuration Example</b>{{< /highlight >}}<br>

A basic resource configuration for an AWS instance might look like this:

```hcl
    resource "aws_instance" "example" {
      ami           = "ami-275f631"
      instance_type = "t2.micro"
    }
```

### {{< highlight go >}}<b>Using `for_each` and `count`</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Lifecycle and Timeouts</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Best Practices</b>{{< /highlight >}}<br>

- Create a file for a bundle of resources that belong together.
- Use modules instead of a complex file structure as the infrastructure grows.

```hcl
    # Example for a resource file
    module "my_module" {
      source = "./modules/my_module"
      # Additional configurations ...
    }
```

## {{< highlight go >}}<b>Terraform Provisioners</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Definition and Usage</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Types of Provisioners</b>{{< /highlight >}}<br>

- **Creation-Time Provisioners**: These are run only during the creation of the resource, not during updating or any other lifecycle event. They are designed for initial resource setup.
- **Destroy-Time Provisioners**: These run when the resource is being destroyed, if specified with `when = "destroy"`.

### {{< highlight go >}}<b>Provisioning Best Practices</b>{{< /highlight >}}<br>

- **Good**: Automating the creation of infrastructure and instance initialization with `user_data` or AWS `cloud-init`.
- **Better**: Using `remote-exec` provisioner on a base AMI to run a few commands upon instance creation.
- **Best**: Building AMIs with Packer to ensure minimal configuration is needed during provisioning.

## {{< highlight go >}}<b>Terraform Data Sources and Outputs</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Data Sources</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Outputs</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Backends in Terraform</b>{{< /highlight >}}<br>

Backends in Terraform are configuration elements that determine where and how the infrastructure state is stored, crucial for collaboration in teams and managing remote operations.

### {{< highlight go >}}<b>Functions of a Backend:</b>{{< /highlight >}}<br>

- **State Storage:** Backends allow storing the state in a remote environment like AWS S3 instead of locally on the disk. This promotes collaboration as the team can access the same state.
- **Locking Mechanism:** To prevent state corruption, some backends, such as Terraform Cloud or Enterprise, offer locking mechanisms that block concurrent state modifications.

- **Sensitive Information:** By using backends like S3, sensitive information is not stored on the local disk, enhancing security.

- **Remote Operations:** For large infrastructures or specific changes, `terraform apply` operations can take a long time. Backends enable these operations to be executed remotely, allowing you to turn off your computer in the meantime.

### {{< highlight go >}}<b>Initialization:</b>{{< /highlight >}}<br>

The `terraform init` command must be called whenever a new environment is set up or any change to the backend configuration is made, to initialize or update the backend.

### {{< highlight go >}}<b>Configuration:</b>{{< /highlight >}}<br>

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

## {{< highlight go >}}<b>Terraform Modules Overview</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Initial Setup with Modules</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>When to Use Modules</b>{{< /highlight >}}<br>

As the project grows (20+ resources and data sources), issues arise:

- Increasing code size.
- Complicated dependencies between resources.
- Large impact on `terraform apply`.

Modules solve these issues by organizing Terraform configurations into folders.

### {{< highlight go >}}<b>Types of Modules</b>{{< /highlight >}}<br>

**Resource modules** (`terraform-aws-modules`), used for:

- Creating resources.
- Minimal inter-module dependencies.
- High flexibility.

**Infrastructure modules** incorporate:

- Specific versions of resource modules.
- Company-wide standards (e.g., tagging conventions).

### {{< highlight go >}}<b>Module Implementation Example</b>{{< /highlight >}}<br>

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

### {{< highlight go >}}<b>Organizing Modules</b>{{< /highlight >}}<br>

Categorize by function:

- **Front-end Services**: Websites, mobile back-end.
- **Back-end Services**: Search, payments, reviews.
- **Shared Services**: CRM databases, monitoring.
- **Base Network**: VPCs, IGWs, VPNs, NATs.
- **Identity**: IAM policies, users, groups.

### {{< highlight go >}}<b>Tips and Best Practices</b>{{< /highlight >}}<br>

Utilize the **Terraform Module Registry** for discovering and using community modules.

- Good Terraform modules have:
  - Clean code.
  - Rich features.
  - Sensible defaults.
  - Tests, examples, documentation.
  - Security, versioning, lifecycle-readiness.

### {{< highlight go >}}<b>Module References Storage</b>{{< /highlight >}}<br>

`.terraform` directory stores module references, allowing immediate access to module changes. Use `tree` or `ls -1` to view the `.terraform` directory contents for modules and plugins.

## {{< highlight go >}}<b>Terraform Troubleshooting</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Potential Issues</b>{{< /highlight >}}<br>

Mismanagement of resources in the cloud can lead to critical issues:

- Accidental deletion of resources.
- Unauthorized addition of critical resources.
- Configuration drift from the intended state.

### {{< highlight go >}}<b>Commands for Troubleshooting</b>{{< /highlight >}}<br>

Terraform provides a series of commands to help manage and troubleshoot resources:

#### {{< highlight go >}}<b>Listing Current State</b>{{< /highlight >}}<br>

To see the current state of resources as known by Terraform:

```shell
    terraform state list
```

#### {{< highlight go >}}<b>Detecting Configuration Drift</b>{{< /highlight >}}<br>

To actively query the current state of the resources and detect any changes:

```shell
    terraform plan
```

#### {{< highlight go >}}<b>Applying Corrections</b>{{< /highlight >}}<br>

To apply the necessary changes to reach the desired state configuration:

```shell
    terraform apply
```

#### {{< highlight go >}}<b>Importing Resources</b>{{< /highlight >}}<br>

If a resource exists in the cloud but not in Terraform's state, it can be imported:

```shell
    terraform import <ADDRESS> <ID>
```

For example, to import an AWS instance:

```shell
    terraform import aws_instance.example i-abcd1234
```

#### {{< highlight go >}}<b>Reconciling State</b>{{< /highlight >}}<br>

The `terraform refresh` command updates the state file with the real-world infrastructure:

```shell
    terraform refresh
```

This is useful for ensuring that Terraform's state matches the actual infrastructure and for detecting drift.

The `terraform state list` command will then list the updated resources known to the state file.

## {{< highlight go >}}<b>Terraform Workspaces</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Understanding Terraform Workspaces</b>{{< /highlight >}}<br>

Terraform Workspaces are used to manage multiple states within the same Terraform configuration, allowing for parallel management of different environments such as development, staging, and production. Each workspace encapsulates a set of infrastructure with its state and variables, enabling changes to be applied without affecting other environments.

### {{< highlight go >}}<b>Advantages of Workspaces</b>{{< /highlight >}}<br>

- **Isolation**: Workspaces keep state and variables separate, reducing the risk of cross-environment changes.
- **Environment Specific Configuration**: Resources can be tailored for specific workspaces using conditional logic within Terraform code.
- **Backend Support**: Workspaces are typically backed by remote state storage like S3, which helps with state sharing and locking.

### {{< highlight go >}}<b>Best Practices with Workspaces</b>{{< /highlight >}}<br>

- **Automation**: Integrate workspace management into CI/CD pipelines for consistency and reliability.
- **Switching Context**: Always ensure you are operating in the correct workspace to prevent unintended changes.

### {{< highlight go >}}<b>Working with Workspaces in Terraform</b>{{< /highlight >}}<br>

#### {{< highlight go >}}<b>Initializing and Selecting a Workspace</b>{{< /highlight >}}<br>

```shell
terraform workspace new <workspace_name>
terraform workspace select <workspace_name>
```

#### {{< highlight go >}}<b>Example Workspace Configuration</b>{{< /highlight >}}<br>

Local values and provider configuration can be adapted based on the workspace:

```hcl
    locals {
      environment   = terraform.workspace == "default" ? "development" : terraform.workspace
      // Other local variables mapped per environment...
    }

    provider "aws" {
      region             = "us-west-1"
      allowed_account_ids = [local.allowed_account_ids]
      // Assume role if necessary...
    }
```

#### {{< highlight go >}}<b>Conditional Resource Creation</b>{{< /highlight >}}<br>

Resources can be conditionally created based on the workspace:

```hcl
    resource "aws_instance" "example" {
      count = terraform.workspace == "prod" ? 1 : 0
      // Other configuration...
    }
```

#### {{< highlight go >}}<b>CI/CD Pipeline Integration</b>{{< /highlight >}}<br>

Automating workspace operations through a CI/CD pipeline is recommended for safety and efficiency:

```yaml
# CI/CD pipeline example for Terraform
build:
  commands:
    - terraform init
    - terraform validate
    - terraform workspace select ${WORKSPACE_NAME} || terraform workspace new ${WORKSPACE_NAME}
    - terraform plan
    - terraform apply
```

### {{< highlight go >}}<b>Handling Multiple Workspaces</b>{{< /highlight >}}<br>

- **Visibility**: Tools or conventions should be used for clear visibility of workspaces and their corresponding infrastructure.
- **Safety**: Care should be taken to avoid applying changes to the wrong workspace.
- **Maintenance**: Regular review of workspaces and their resources ensures they remain aligned with their purpose.

## {{< highlight go >}}<b>Utilizing `for_each` in Terraform</b>{{< /highlight >}}<br>

### {{< highlight go >}}<b>Creating Multiple IAM Users</b>{{< /highlight >}}<br>

```hcl
    variable "user_names" {
      description = "Create IAM users with these names"
      type        = list(string)
      default     = ["neo", "trinity", "morpheus"]
    }

    resource "aws_iam_user" "example" {
      for_each = toset(var.user_names)
      name     = each.value
    }

    output "all_arns" {
      value = values(aws_iam_user.example)[*].arn
    }
```

This example creates IAM users for each name in the `user_names` list and outputs their ARNs after `terraform apply`.

### {{< highlight go >}}<b>Looping Over Inline Blocks in Resources</b>{{< /highlight >}}<br>

```hcl
    resource "aws_autoscaling_group" "example" {
      # (...)

      dynamic "tag" {
        for_each = var.custom_tags

        content {
          key                 = tag.key
          value               = tag.value
          propagate_at_launch = true
        }
      }
    }
```

The `dynamic` block with `for_each` loops over `custom_tags` and creates tags for the autoscaling group.

### {{< highlight go >}}<b>Using `for_each` with Expressions</b>{{< /highlight >}}<br>

```hcl
    variable "names" {
      description = "A list of names"
      type        = list(string)
      default     = ["neo", "trinity", "morpheus"]
    }

    output "upper_names" {
      value = [for name in var.names : upper(name)]
    }

    output "short_upper_names" {
      value = [for name in var.names : upper(name) if length(name) <= 5]
    }
```

The first output transforms all names to uppercase, while the second output includes only names with 5 or fewer characters in uppercase.

### {{< highlight go >}}<b>Conditionals with `for_each`</b>{{< /highlight >}}<br>

```hcl
    dynamic "tag" {
      for_each = {
        for key, value in var.custom_tags :
        key => upper(value) if key != "Name"
      }

      content {
        key                 = tag.key
        value               = tag.value
        propagate_at_launch = true
      }
    }
```

This dynamic block uses a `for` expression with a conditional to exclude certain tags.

### {{< highlight go >}}<b>Limitations and Capabilities</b>{{< /highlight >}}<br>

- Cannot use `count` and `for_each` within the same resource block.
- From Terraform 0.13 and up, it's possible to use `for_each` and `count` together within module definitions.

The `for_each` argument allows Terraform to create multiple instances of a resource or module. It loops over a given collection and creates one instance per item. Conditionals can be used to filter or modify the collection. The outputs can then collect the attributes of the created resources.
