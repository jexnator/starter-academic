---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "01/07/2024 - 12/07/2024"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2024-07-10
lastmod: 2024-07-10
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

- Discuss the current apprenticeship status with the new PiBS lead, i.e. Andreas and Mergim, and plan the next steps.
- Completion of internal NoSQL module by the end of calendar week 28.
- Find a way to archive the existing Microsoft 365 backup of the old tenant, which is currently stored in Rubrik RSC.

## What did I do?

There were a few internal IT tasks in the past week 27. With regard to the Microsoft 365 migration to the Vinci Tenant, there were still some relics to be decommissioned that are now obsolete in the new environment and therefore cause unnecessary costs. This included various shared mailboxes and generic E3 accounts.

I also set myself the task of updating our IT inventory in ITSM, as this no longer matched the reality. The problem for this discrepancy is a missing offboarding task, which should inform the internal IT that the IT inventory needs to be updated when there are leavers. I added this task to Personio so that it would not be forgotten in future. There were also quite a few new devices missing from the inventory, which we purchased for employees after they were entitled to a new device after every 3 years. I have taken this point on board and will communicate it at the next internal IT meeting so that the respective purchaser is aware of this responsibility in future.
While we're on this subject, it's worth mentioning that Kiru has requested the order of a new Lenovo X1 ThinkPad from us. I configured it together with him and ordered it from the Lenovo Pro Shop. However, due to our new company name and clean payment processing, we had to request changes to our company information (name & e-mail address) via a ticket from Lenovo Invoicing beforehand, which was a bit of a pincer job.

Another task was the password rotation of all our generic accounts. In this regard, we also had the ownership of our shared mailboxes, which had previously been with Dan, transferred.

In the Keeper Tenant, there were also some important changes to be made to the company information due to last year's rebranding. On the one hand, we had the main contact transferred from Sämi to the internal IT department, and on the other hand we had the company information and the Keeper support account adjusted via a ticket. We also submitted a request to Keeper for a KSM (Keeper Security Manager) subscription, which Gian needed for programmtic access with regard to his SSL automation. A Keeper sales representative then contacted us and we had a short meeting with him to explain the exact use case. Unfortunately, it turned out that the subscription cannot be assigned to individual users, but only tenant-wide, which makes the annual price dependent on how many seats (users) you have in Keeper (for our tenant with 50 users, that would be a whopping \$2,600 per year). Gian and I then argued that we would only need programmatic access with KSM for this one technical user in order to retrieve the passwords for each LAB cluster every 90 days. For this reason, a subscription for the entire tenant, i.e. all users, would not make sense for us, but would be very expensive. Of course, we checked beforehand how much the whole thing would cost with the AWS Secret Manager and presented this to Sales, which would be significantly cheaper for our use case at \$100 - \$120 per year. In the end, we decided that he (Sales) would now check whether Keeper could make an exception there and accommodate us with the price accordingly.

There was also a small incident with our website. Sonja reported that she was being spammed by notifications sent via the various contact forms on our website. This resulted in around 500 notifications coming in via a spambot over a short period of time. Together with Oli, we then investigated the cause of this problem. It turned out that human verification (via an invisible ReCaptcha) had been activated on our website up to that point, but the various contact forms were integrated via Hubspot and there was no corresponding configuration.

In addition to these tasks, there were a few other things to do, such as decommissioning the LAB/Hubspot/Keeper accounts for the public cloud leaver or initiating the Keeper/Hubspot accounts for the new Sales Alan. In the meantime, I also spent a few hours preparing for the exams.

## How did I improve and what will I do different from now?

After an intensive examination phase, I'm looking forward to four weeks off school. The long screen time has led to a lack of physical exercise and vitamin D deficiency, which I want to make up in the summer holidays.

In addition, the significant deviation in the IT inventory showed me how important control tasks and reminders are. The actual-to-target ratio deviated considerably due to the lack of control or reminder mechanisms. This also shows me again how important it is to work with tools such as MS ToDo in everyday life so as not to forget anything, to be able to prioritise better and to schedule tasks accordingly.

<br>
<div style="padding: 18px; padding-top: 10px; color: #eee; background-color: #3c3c3c; border-radius: 10px; box-shadow: 0 4px 8px rgba(0,0,0,0.2);">
  <h2 style="text-align: center; color: #ccc;">Work distribution this weeks</h2>
  <div style="background-color: #505050; padding: 15px; margin-bottom: 20px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>internal modules (10%)</strong>
    <div style="width: 10%; height: 30px; background: linear-gradient(to right, #607D8B 0%, #B0BEC5 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
  <div style="background-color: #505050; padding: 15px; border-radius: 8px; color: #eee; box-shadow: inset 0 2px 4px rgba(0,0,0,0.1);">
    <strong>other tasks (90%)</strong>
    <div style="width: 90%; height: 30px; background: linear-gradient(to right, #FF5722 0%, #FFCCBC 100%); border-radius: 5px; margin-top: 10px;"></div>
  </div>
</div>
