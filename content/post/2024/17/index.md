---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "26/08/2024 - 13/09/2024"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-09-13
lastmod: 2024-09-13
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

## What are my actual goals?

- Organize internal IT tasks related to onboarding, hardware support, and network management.
- Finalize the setup for the new employee’s hardware and accounts.
- Continue work on my FFHS transfer and seminar projects, including the choice of topics and practical implementations.

## What did I do?

In internal IT, I worked on several tasks. I ordered a Lenovo notebook and coordinated with Etavis to stage the Vinci image onto the device. After receiving the notebook, I inventoried it in ITSM Ky2Help. I also created the necessary accounts for the new employee and recorded the process via screen recording for the rest of our internal IT team.

Martin experienced hardware issues with his Lenovo X1 Carbon Gen 12, which required a repair. I handled the case with Lenovo Support, diagnosing the problem and organizing an onsite visit for a motherboard and battery replacement. In addition, I replaced a ROOMZ display battery and created new WiFi guest access cards for the VES-GUEST network.

Nicolas and I analyzed our Microsoft 365 accounts to review where E3 and K licenses are being used. Since E3 licenses in the Vinci contract are significantly more expensive, we identified areas where K licenses would suffice. I also terminated AWS Labs of former employees in our OU and decommissioned an old BI tool implementation by terminating the CloudFormation stack which was back then generated via AWS CDK. As usual, I conducted the weekly cost review of AWS OU accounts.

On the academic side, I worked on finding a suitable project for my semester paper in the MCI (Mensch und Computer Interaktion) module at FFHS. I discussed possible use cases with Rebecca, but we couldn't identify a clear improvement on our website in terms of the user interface. I then decided to focus on Vinci's EasyVista IT-Self-Service Portal, which has significant UI improvement potential in different areas.

I also finalized my topic for the seminar paper in the Fall semester 2024 at FFHS. I would like to compare four different Infrastructure as Code (IaC) tools: Terraform, OpenTofu, Pulumi, and Ansible. The work will be divided into two parts: first, defining quantitative comparison criteria and reviewing existing literature; then, conducting the engineering phase, where I will implement the same example infrastructure with all four tools. Based on the results, I will create a guide highlighting the pros and cons of each tool.

Parallel to these tasks, I continued writing the theoretical part of my transfer project. I completed chapters 2 (Previous Research) and 3 (Situation Analysis). Next, I will document the practical product I developed, focusing on the automation tool I created for WordPress in AWS Lightsail.

## How did I improve and what will I do differently from now?

The past two weeks have reinforced the importance of clear documentation, especially for tasks which are recurring. Documenting account creation via screen recording was a new experience for me. I think it takes a lot less time if you write your own documentation for the process with screenshots. That's where I get feedback from my colleagues. If my hypothesis is confirmed, I will keep this approach for future documentation.

I had a bit of trouble finding a suitable topic for the seminar paper at the beginning. This probably had something to do with the fact that I was still in the middle of writing the transfer thesis and didn't want to start thinking about the next one. That's why I'm glad that I've now found a topic and have already been able to think about the exact methodology and approach. The more precise the preparation and delimitation, the easier and quicker the subsequent elaboration, as I have realised in my previous work in this field.

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this weeks</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>TA, Sema & MCI Semester Work (60%)</strong>
    <div style="width: 60%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (40%)</strong>
    <div style="width: 40%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
