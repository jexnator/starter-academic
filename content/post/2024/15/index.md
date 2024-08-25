---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "12/08/2024 - 16/08/2024"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-08-16
lastmod: 2024-08-16
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## What are my current goals?

- Finalize the engineering part of my transfer project (TA) by addressing SSH agent forwarding issues on Windows.
- Start the new semester at FFHS after the summer break.
- Explore a backup solution for the old Amanox SharePoints on Amazon S3.

## What did I do?

The summer holidays are over, and classes at the FFHS have resumed. This week, I focused on advancing the practical part of my transfer project, which involves automating the update and migration process for WordPress Bitnami instances on AWS Lightsail. This tool aims to reduce recurring manual tasks for hosting administrators who manage WordPress environments on AWS Lightsail and has been made publicly available on [GitHub](https://github.com/jexnator/wordpress-bitnami-lightsail-patch-migrate-update) so that others can benefit from it as well.

WordPress Bitnami instances on AWS Lightsail cannot have their LAMP stack components updated individually. To keep the environment up to date, a new Lightsail instance must be provisioned with the latest Bitnami image, followed by a content migration from the old instance. The tool I've developed automates this process using Terraform, with SSH agent forwarding to securely migrate data without moving private keys between servers.

The tool works well on Unix-based systems (I primarily use macOS). However, I encountered issues when attempting to run the same automation on a Windows machine. Specifically, Terraform's remote-exec provisioner on Windows only supports Pageant as the SSH agent, while I planed to implement it with OpenSSH. This caused execution failures during the migration process.

To troubleshoot, I manually tested the SSH agent forwarding in PowerShell on Windows. After adding the private key to the agent and establishing an SSH connection from one remote instance to another, I was able to execute the necessary migration commands successfully. However, when trying to automate this process using Terraform, the provisioner failed because it only supports Pageant for SSH authentication on Windows. :-(

Aside from this engineering work, I also dealt with internal IT tasks related to backing up our old SharePoint sites from the Amanox tenant to Amazon S3. Initially, I considered using a Python script to download the data via the Microsoft Graph API and upload it to S3 with Boto3. However, the Graph API encountered issues with larger files, sometimes returning a 503 Service Unavailable error. I decided to switch to using Rubrik RSC for exporting the data archives and then uploading them to S3 using the AWS CLI (aws s3 sync), which proved to be a faster and more reliable solution.

## How did I improve and what will I do differently from now?

The issues I encountered with SSH agent forwarding on Windows highlighted the importance of understanding platform-specific limitations when developing cross-platform tools. Unfortunately, it turned out once again that you can't trust a tool like Terraform to work the same way on Windows as it does on MacOS. In future, I will have to focus more on clarifying such inconsistencies in advance so that this can be known and avoided earlier.

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this weeks</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>TA (70%)</strong>
    <div style="width: 70%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (30%)</strong>
    <div style="width: 30%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
