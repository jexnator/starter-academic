---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "19/06/2023 - 14/07/2023"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2023-07-11
lastmod: 2023-07-14
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

During the last few weeks I already mentioned that I had a few support calls with a Rubrik engineer about the SSO-Integration in AzureAD. Meanwhile we could fix the bug, which appeared during the configuration according the steps in the rubrik documentation. The problem was that we were using AzureAD from within the Entra Microsoft Admin Center, rather than directly through the Azure portal. The functionality of the Azure AD should be the same, but it seemed that there were some differences between the two user interfaces depending on whether you access our IDaaS directly via Portal Azure or via the Entra Admin Center. All in all, we have successfully completed the SSO integration with this. Finally, I created documentation that describes how to configure the whole thing from scratch and how to update an expired SAML certificate.

For the upcoming Q3 info meeting, I created the slides for Dan's Ciso Corner for our M365 Rubrik Backup to give employees a glimpse of what we've implemented and the capabilities we now have as a result.

Following that, I set about my next internal IT task, which involved cleaning up our AzureAD tenant. We have now decided to permanently delete employees who are no longer with us. The accounts had been hanging around mainly to preserve the authority of files for example in SharePoint. After a short research on my part, it turned out that this metadata is not removed, even if you delete the users permanently. In MS Teams it is the case that the users are declared as "Unknown User" after 30 days (caching), although the user is deactivated but still present in AzureAD. This means that "leaving" the users in Azure AD only causes us unnecessary effort, since you have to manually delete the users from existing groups. Furthermore, various groups and enterprise applications have been deleted that are no longer necessary or are no longer used.

Another goal is to automate our AzureAD using a CI/CD pipeline hosted in our GitHub. This could look something like our Vending Machine for AWS accounts, but a bit more elaborate due to the additional functionalities. Fäbl has instructed Gian and me on this and explained to us how we can implement it. We will work on it in the meantime and do reviews with Fäbl.

It is also worth mentioning that we have decided to set up 4 additional workstations with wide screens in the internal IT. Gian and I were responsible for the order. In the process, we jointly made a mistake. Part of the delivery was shipped to Martin's home address. Fortunately, we were able to redirect the four large screens to our company adress in time. Nino set up the new workstations afterwards, since Gian and I were not present on Thursday and Friday due to exam preparation.

Another task was to clean up the AWS organisation and accounts. The goal was to create a unified order within our organisational units. First I had to familiarise myself with our AWS Vending Machine, as this had to be done within the rivendell-controller pipeline to ensure Terraform maintained the current state of the organisation. I ran some tests and moved my personal lab account over the account JSON file. In doing so, I wondered if it was possible to customise the Lab name of an existing account, as some accounts in our organisation do not conform to our naming conventions. Unfortunately, this second test resulted in my personal Lab account being suspended. I should have known this after the change Raphael made to the Rivendell project. When the name is adjusted, the underlying JSON file no longer exists, and the account is closed by the attribute "close_on_deletion = true". I then had to log into my AWS console via root and have the account reactivated via support.

After this procedure, I was able to take back the reigns of my Lab account. :-D
However, this led to a build error in the rivendell-controller pipeline. Since Terraform did not recognise the current account directly, it tried to create a new account. But this did not work because the account is already linked to my personal email address and an email address can only be used once. I tried to solve the problem, but unfortunately had no success, as I had no practical experience with Terraform yet. I now turned to Fabian, who will help me to solve this problem. It will probably come down to deleting my existing account and me creating a new account with a Leaf email address. The effort for this is less than making a change to the productive code, which would only be temporary anyway and would have to be undone after.

I have also created a guide for our AWS Cost Monitoring. This is mainly so that I can hand over this task to someone else when I am on holiday. The document has now been filed in our internal IT to properly document the process.

I spent the remaining days during week two and three preparing for the final exams. Now we are off from school again for a moment and thus have a slightly less stressful time, which is very convenient for me to refresh myself mentally. This summer I will spend in Switzerland, because I still have several to-dos in my private life.

Finally, I would like to point out that I will concentrate primarily on the internal modules until the end of the year and that I will be a bit leaner in the internal IT and lab team. I have been a bit too busy with the interesting tasks lately and neglected the curriculum of the internal modules concerning AWS a bit too much. I have created a schedule for Dom and Dan to illustrate when I expect to be finished with the public cloud modules.

I will spend the next two weeks on holiday.

</p><br>
<p></p>
