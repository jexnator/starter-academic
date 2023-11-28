---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Monthly Review 21/08/2023 - 29/09/2023"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2023-08-31
lastmod: 2023-08-31
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
### Week 1
In our PiBS studies we complete a communication module in which we focus on our personal appearance and intercultural skills. The practical part of this module includes a 3-day course in a Ticino theater school, which we were able to attend as a class this week.

On Tuesday evening, we set off as a class to Verscio. Verscio is a small village below the Maggia Valley. We arrived in Locarno around 8am and then took a bus to Avegno - a village right next to Verscio, where we checked into our bungalows at the Picolo Paradiso campground for the next 3 days.

The next morning we took the Centovali Express to Verscio to the theater school "Accademia Teatro Dimitri" where we were welcomed by our director of studies together with the two course leaders Hans-Henning and Diego.

The first day was mainly about getting to know each other better and finding out how far you can go personally until you leave your comfort zone.

During the second day, we were shown and taught that before communicating with another person, it is important to first establish a connection with them and maintain it throughout the dialogue.

The third day was mainly about acting out what we had learned in small theater sequences and reflecting on how we personally (internally) feel as a performer and how the whole thing is viewed by the audience from the outside (externally).

The exercises we did during the course were very different. Partly we were on a mat and in my opinion we did a kind of yoga, where Hans-Henning navigated us through. Partly we did exercises together in a big circle, partly we put ourselves in the position of a water plant and had to move or dance like one, partly the exercises were of a sportive nature and as already mentioned, we also did theater sequences.

I could not always understand what exactly we were doing in certain exercises and in what way this should help us as students in our daily work. Personally, I think that the course instructors, due to their experience in the theater sector, have completely different views of life and are sometimes also a bit more spiritual than people in the IT sector. Nevertheless, the workshop was fun and I was able to draw some lessons from it regarding personal appearance during a dialogue or a communication such as body posture, eye contact and presentation technique.

A very positive side effect was also the strengthening of class cohesion. I think that through the workshop and the free time in between, we really got to know each other for the first time and, above all, got into closer contact with people with whom we normally didn't have much to do.

All in all - a somewhat different, but successful and interesting working week.

### Week 2
This week started with creating the O365 account for a new sales person. This included capturing the data in Azure AD, adding the correct groups, applications and licenses. The next step was to create the Hubspot account.

This week Fabian, Nino, Gianluca and I were involved in the IT migration. On Thursday, this allowed us to participate in a first messaging migration workshop conducted by our French Vinci Energies colleagues. 

During the rest of the time I worked on the CloudSec module, finalizing it and filling in the feedback form accordingly. The learnings in module can be found in the publication "Cloud Security in AWS". Then on Friday I started with the theory of IaC&DevOps with Terraform module, in which I was taught the basics of DevOps in the "Day 1" chapter. This included the term definition of DevOps, meaning Development + Operations. Additionally, I am now aware of what DevOps encompasses for Keyconcepst and what opportunities arise from it such as CI/CD, IaC, Microservices and improvements in communication, collaboration and monitoring & logging. I'm looking forward to diving deeper into the topic and the diversity of the module as it was written by different coaches or staff and thus written from different perspectives.

By the way - this week we were in Croatia in the Workation. I shared my isights about it with Rebecca, who posted a post about it including a video on LinkedIn.

### Week 3
During this week, I focused on gathering important information required for the domain transfer to Vinci Energies. In a first step I made sure to look into the continuation of essential services like email and our website. It's important to have zero downtime during this transition. Then I secured the complete dump-file of the DNS zone along with the authentication code for the transfer. I then released the domain tranfer protection. I checked also if there are specific SPF records in the dump-file and outlined them.

In the future, MX, NS and TXT records will be managed by VESI. However, we will still have the ability to manage A, AAAA and CNAME records locally.

On Wednesday I had the Weekly with Alessandro to discuss the progress of the migration and the next steps with each other.

In between, some internal IT tasks were due. These included resetting our former marketing employee's laptop so that she can continue to use her notebook privately. I also changed Sonja's monitor. She felt the need to test a widescreen monitor, which we found to be good and therefore put into practice.

### Week 4
Since we at Vinci only have the choice between Lenovo and Apple devices in the future, I contacted the Surface users, exchanged ideas with them about their needs and then ordered them the new Lenovo devices.

Afterwards I tested a software package on one of our clients with John-Nathan from Vesi. Unfortunately, we discovered that part of the installation could only be carried out in the new Vinci Energies network. We agreed to install the antivirus software in advance to meet the requirements of the new network.

I then worked on the messaging migration. Here I filled out some Excel sheets.
The Cortex training was also scheduled for this week. We from internal IT were each given an admin account at Vinci to make changes in the Cortex XDR console, such as temporarily disabling endpoint protection on individual clients.

At the end of the week we had the weekly with Alessandro and the weekly with our French colleagues at VESI.

### Week 5
Fünfte Woche:
- Migration - Austausch mit AD Team betreffend den zu migrierenden SSO-Apps
- Call VOIP-Teams Vorabklärungen mit Alessandro und Vuz
- Installation Cortex Agent auf Test-Client.
- Weekly mit Alessandro - weiteres Vorgehen definieren, was wird er am Infomeeting bekannt geben, was soll er aus unserer Sicht (interne IT) noch bekannt geben-> Inputs geben von interner IT Sicht, 
- Abklärungen Software-Installation mit John-Nathan

Sechste Woche:
- Migration
- Abklärungen SSO
- Skript schreiben betreffend E-Mail Grösse
- Sales Enabelment Workshop 2

Siebte Woche:
- Anleitung erstellen Installation Cortex Agent und verschicken an Mitarbeiter
- Check AWS SSO
- Skript ausführen betreffend E-Mail Grösse
- Weekly
- Bestellen Notebooks für Armstrong und David
- SSO-Applikationen mehrere Meetings
- Dispositionsgespräch

Achte Woche:
- SSO Integration Kyberna (failed)
- Information Mitarbeiter (Neues Netzwerk, Clara Accounts, zu grosse E-Mails für Migration)
- Unterstützung Adrian PC Einrichtung

Neunte Woche
- Drucker SMTP
- Teams Migration Absprache mit Sepp und Alessandro
- Mails verschicken: E-Mail Grösse
- SSO Migration
- Skripts schreiben für Aktivieren und Deaktivieren von Windows Hello for Business
- Absprache & Bestellen Device für Andreas

</p><br>
<p></p>
