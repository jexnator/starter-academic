---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Amanox IT Migration"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2023-11-28
lastmod: 2023-11-28
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
### Short Summary
The acquisition of Vinci Energies has resulted in some changes to our internal IT at Axians Amanox AG. In short, the company accounts and the M365 subscriptions and the Windows clients were migrated to the centrally managed Azure AD Tenant of Vinci Energies, the Amanox Azure AD Tenant was terminated, the domain "amanox.ch" was transferred,the SSO applications were reassigned and we got a new network and new access points in our office.

### Milestones
The following dates were relevant for the migration work and preparations had to be made accordingly:
<b>Network change</b>: Week 23/10 & 24/10
<b>Pilot tests software</b>: 25/10
<b>Clara AD / SSO / installation software on all Windows clients</b>: 08/11 & 09/11
<b>Messaging migration</b>: 15/11

### Preparation
In order to prepare ourselves on the Amanox side and on the VESI and Vinci side, we held an initial workshop at an early stage to prepare for the migration. The responsible departments agreed in advance what was to be migrated and how. Now it was a matter of bringing everyone involved up to the same level, allocating responsibilities and getting to know each other, which was done by the project manager of the externally grown Vinci team, Georges. It was also announced that we would meet weekly in the form of a meeting - once with just the Swiss, i.e. Vesi, and once with the entire migration team - to discuss the progress of the migration. The above-mentioned network change was carried out independently by Sämi together with Vesi Switzerland, which is why it will not be discussed in much more detail here.

### Xavier's Preparation Tasks
Before the actual migration, I was mainly concerned with preparing for the messaging, domain, SSO & client migration. 

#### Messaging & M365 suite
For the messaging migration, I filled Excel lists with the required information in order to complete the migration of Outlook (emails, accounts, shared calendars & resources), SharePoint and OneDrive. To make this process more efficient and minimize human error, I worked as much as possible with PowerShell in the admin centers to get the required information in the form of CSV files. During the preparatory work, Georges announced that only mails + attachments with a maximum size of 25 MB could be migrated. This encouraged me to write a PowerShell script that interacted through all our mailboxes and memorized the subject line of the emails that were too large so as not to lose any important data. I was then able to inform and sensitize the affected employees that they should save the mentioned content somewhere before the actual migration, if still needed.

#### Domain Transfer preps
Our domain "amanox.ch" was previously hosted by us at AWS. The aim of the migration was to transfer the domain to Vinci and its provider. To do this, I collected all DNS entries, deactivated the transfer lock and generated the auth code for the transfer. I then transferred the information to Georges via a OneNote.

#### Windows Clients
For the Windows clients, it was decided that the devices would be domain-joined, SCCM would be set up for various installations/regulations and ZScaler and Cortex would be installed for VPN and virus protection. As no Windows master image was available for the Lenovos at this time, it was decided to carry out the installations via PowerShell scripts. Due to the network changeover, it was mandatory to install Cortex on all Windows devices beforehand + to adapt the host name according to the naming convention. I tested the belonging scripts together with John-Nathan. After successful testing, I wrote a short guide, so that our employees could carry out the installation themselves. The next step was to test the remaining software packages. However, this was tested by Dan, the rest of the IT team and various guinea pigs, as I was on vacation in the meantime.

#### Enterprise Applications
The toughest part of the preparation was probably the SSO migration, in which all existing enterprise applications were migrated to the Vinci AD. The individual enterprise applications were each to be processed by Vinci in the form of tickets and migrated to their AD, which we strongly criticized at the beginning due to its susceptibility to errors and an unnecessary additional formal effort. We were then able to negotiate that the most critical applications would be migrated live via a Teams meeting together with the Vinci AD admins. For the remaining applications, I then collected the relevant SSO documentations for each application and noted down what Vinci needed from us as the Identity Provider and what we needed from the service provider's point of view. I was then able to transfer most of the applications before the actual migration, except for the most critical ones, which could still be migrated away on the exact day of migration or one or two days later.

### The actual migration
Overall, the migration of the IT systems went successfully and largely without any problems. The new network was put into operation in the office on schedule and all Windows clients had the obligatory Cortex antivirus software pre-installed. The client migration went smoothly for the most part, with the exception of a few cases where Windows Hello did not work temporarily, but this was subsequently rectified. The domain transfer was a little less coordinated. Due to communication difficulties, the lab environment and our website were down for a few hours, which we only noticed by chance. The subsequent messaging migration went mostly well, apart from some faulty OneNotes, configuration issues in shared calendars and missing SharePoint permissions etc.
A particular benefit was the week-long special support, which allowed us to communicate issues and concerns directly via a Teams chat instead of having to create numerous tickets.

### Reflection
This IT migration proved to be extremely instructive for me and my professional development. The weekly meetings with the Swiss and French colleagues gave me the opportunity to expand my technical knowledge, improve my English skills and gain valuable insights into interpersonal relationships and cultural differences. In retrospect, various things could have been handled a little differently and probably more straightforwardly on both sides, but I believe that in the aftermath there is usually room for improvement in every matter, which is why I don't want to go into every single complaint here.

I would like to thank everyone who was involved in the migration and helped to ensure that it went so smoothly. A big thank you also goes to Dan for his trust in me and his amazing efforts in the area of employee support after the messaging migration. I would also like to thank Alessandro, Sepp, John-Nathan and Georges for their commitment and help.

Well, I will keep you posted and we will hear us next week again. :-P

</p><br>
<p></p>
