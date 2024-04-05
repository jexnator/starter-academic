---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "25/03/2024 - 05/04/2024"
subtitle: "Ski weekend @Amanox"
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-03-14
lastmod: 2024-02-14
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
At the end of the IaC and Devops module, I would like to consolidate the theory and best practices learned with a small hands-on project with the provision of infrastructure in AWS with Terraform. At the same time, with this hands-on part I would like to counteract a real problem in the DNS area of our website. The problem requires a deeper understanding of the topics DNS, SSL/TLS termination, VPC peering, EC2 instances + application & network load balancer, which I will deal with. Furthermore, I would like to create the presentation for the module and hold this.

## What did I do?
Last week, the cooking event organized by Fabian took place at Loeb in Bern, which Gian, the PiBS coaches and I attended. Together with Janine, we prepared various Italian delicacies and had a great evening with the subsequent meal, which we then rounded off at the Hotel Bellevue. Thank you Fäbl & Janine for the organization and execution.

In the hands-on Terraform part, I started by setting up a simple basic infrastructure for operating a web server with a VPC, subnet, route table, Internet gateway, security group, network interface and EC2 instance. I then expanded the project using Route 53 (domain + hosted zone) and an SSL/TLS certificate.

The next step was to address the actual problems we are currently facing with Vinci's DNS provider and our website. We currently have the problem that Vinci's DNS provider does not have the option of pointing to the DNS name of the Lightsail load balancer for our domain using DNS A records (this was possible in Route 53). In addition, no ANAME or ALIAS constructs can be created, as is sometimes the case with other DNS providers. Instead, we currently have to point to the dynamic IPs behind the load balancer with 3 A-Records, which is only a temporary solution, as the IPs behind the ELB change approx. every 2 weeks and therefore the entries always have to be updated.

I then expanded the existing infrastructure with an NLB, an attached eIP (static IP) and 2 target groups. With an additional redirect mechanism on the web server, I was then able to solve the problem. The hands-on task was thus completed. However, it is still necessary to evaluate whether the solution is financially worthwhile and whether the configuration effort involved in updating the web server is worthwhile and justified.

I also created the presentation at the end of the presentation and then gave it on Friday.

## How did I improve?
I was able to expand my skills in the Terraform area. I now have a more detailed understanding of DNS administration, the different record types, SSL / TLS termination and generally deploying cloud resources via IaC.

## What went wromg / will I do different from now?
I failed at the presentation. I wasn't prepared enough, I read off too much, I couldn't get the topic across as intended, the use of the available media wasn't convincing and I couldn't impress with my body language. Next week I will look at these points again and come up with solutions/strategies that I can use to improve and progress personally in these areas.

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this week</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>internal modules (90%)</strong>
    <div style="width: 90%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (10%)</strong>
    <div style="width: 10%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
