---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "12/08/2024 - 16/08/2024"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-08-23
lastmod: 2024-08-23
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

Transition the automation tool for Windows users to a WSL approach due to limitations with SSH agent forwarding in Terraform's Remote Provisioner.
Resolve the archival strategy for our old Microsoft 365 tenant's data in Rubrik RSC.
Decommission the old Microsoft Entra ID tenant and Microsoft 365 services after finalizing the data archival plan.

## What did I do?

In relation to my transfer work, I focussed this week on an important fix to the automation tool to ensure that Windows users can use the automation without restrictions. After several failed attempts to get SSH agent forwarding via Pageant to work within Terraform's Remote Provisioner on Windows, I made the decision to switch to using WSL. Pageant's configuration was too complex, and after multiple trials, I was unable to achieve the desired result. The WSL approach worked as expected with OpenSSH.

In internal IT, Nicolas and I have revised our archiving strategy for the old Microsoft 365 client's data stored in Rubrik RSC. Originally, we planned to create an archive location in S3 to move the backup data and cancel our Rubrik subscription. However, after further research and discussions with Rubrik support, we realised that Microsoft 365 objects cannot be archived to an archive location. On a positive note we realised that our Rubrik subscription for Microsoft 365 runs until 2026 and has already been paid for in advance. This means we have access to Exchange, Teams, OneDrive and SharePoint data until then, which meets our retention requirements.

Given this new information, we decided to focus on archiving the most critical data, specifically the old SharePoint archives, by downloading the archives from Rubrik RSC and uploading them to AWS S3 via CLI. This allows us to access the respective data quickly in case of an emergency which, however, should probably not be the case.

Following the completion of the archival strategy, Nicolas and I finally decommissioned our old Microsoft Entra ID tenant and associated Microsoft 365 services. This will eliminate any ongoing subscription costs related to the old tenant. We chose to retain the empty tenant as a testing ground for potential future use cases or experimentation.

## How did I improve and what will I do differently from now?

The switch to WSL for Windows users in the automation tool has shown me the importance of having flexible alternatives when dealing with platform-specific issues. In this case, avoiding Pageant and moving to WSL allowed the tool to function uniformly across platforms, which saves users from unnecessary configuration overhead.

In terms of IT management, the lesson learned from the Rubrik archival process is to always verify subscription details and available options before making significant changes. Our misunderstanding of the Rubrik subscription timeline led to unnecessary stress and discussions, which could have been avoided with more thorough planning.

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this weeks</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>TA (60%)</strong>
    <div style="width: 60%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (40%)</strong>
    <div style="width: 40%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
