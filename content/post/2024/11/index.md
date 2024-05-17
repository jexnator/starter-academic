---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "06/05/2024 - 17/05/2024"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-05-15
lastmod: 2024-05-15
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

These weeks I am concentrating on working on and completing the Iaas module. The aim is to expand my knowledge of IaaS in AWS, i.e. EC2 (Instances, AMIs, Usage Types, Instance Storage Types) and VPC (Regions, AZs, Subnetting, different Gateways, VPC Peering, VPN & Direct Connect), to deepen the material by means of practical tasks and to carry out the presentation in CW20 or 21. Furthermore, I would like to take a look at practice tests for the AWS certifications Cloud Practioner and Solution Architect Associate to see where I stand with my AWS knowledge.

## What did I do?

In the meantime, there were a few internal IT tasks to take care of + the management of the IT mailbox. This included troubleshooting our Vinci IoT network together with Sepp, which had a misconfigured VLAN tag due to a network update and therefore the DHCP could no longer dynamically assign IPs to the clients. This maneuver also caused the ROOMZ sensors to fail, which required a new network configuration that could only be transferred to the Windows host via cable by pairing. I also replaced the defective docking station in the meeting room, paired the decoupled Poly Bluetooth remote control, replaced the screen at the boss's desk and coordinated the choice of new work devices with the new employees. In addition, DSN A-Records of our Lightsail load balancer (website) on the IT-Vinci side had to be adjusted again according to the dynamic IPs so that the website is still accessible at root domain level.

I was able to make good progress in the IaaS module. Although the tasks are instructive and I enjoy working on them for the most part, in my opinion they are sometimes defined too vaguely by this author. In other words, it was or is not always clear to me what exactly the end result should be and whether the implementation, as required, is even possible. Sometimes it seems to me that this author was in a hurry while working on the modules at the end of his Amanox career. While we are on this subject, it should also be mentioned that, in my opinion, this author's modules are very detailed and demanding and are rather time-consuming due to the large number of tasks, which is why I sometimes miscalculate when it comes to time planning. Finally, I have to honestly admit that I wasn't always really enthusiastic about his modules beforehand and, looking back, I sometimes ducked them a little and in the meantime was instead more excited about the "P" in the abbreviation "PiBS". It is important to mention that I am not referring to the interest of the topics learned or to be learned in the modules, but to the way in which this energy-driven author tried to convey them and the nature of the author himself. Anyway, let's close this box and look positively to the future.

I was able to complete the IaaS module this week with a presentation. I tried to improve on the individual topics compared to last time. I paid special attention to the slides. I tried to work as much as possible with graphs or diagrams, without a lot of text, which I think has already paid off. Thank you for your feedback Dominik and Fäbl and your time. :-)

|                  |                                                        |
| ---------------- | ------------------------------------------------------ |
| GitHub           | [GitHub](https://github.com/JEX-98/aws/tree/main/Iaas) |
| IaaS Publikation | [IaaS Publikation]({{< relref "/publication/IaaS" >}}) |

## How did I improve and what will I do different from now?

Looking back, the Mental Health Workshop has once again made me, like probably others, aware of the 4 areas (personal values, performance, relationships & body) on which our mental health depends and how one can determine or influence the current status in these areas. Over the last few months, I've caught myself saying a few times that I don't have enough time for physical balance/fitness at the moment. However, thanks to this workshop, I was able to realize that you can't have too little time, but that you simply have to make time for this balance. I have now made a personal agreement with myself that I will do a sporting activity at least once a week to compensate for this, which I have already been able to do in the last 2 weeks with 2 slackline sessions in Steinhölzli near Weissenbühl. I also set myself the goal in the area of personal values of being able to say "no" from time to time instead of politely saying "yes" to everything, both professionally and privately.

![Life balance model according Trappitsch](life-balance.jpg "Life Balance Model according Trappitsch")

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this week</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>internal modules (85%)</strong>
    <div style="width: 85%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (15%)</strong>
    <div style="width: 15%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
