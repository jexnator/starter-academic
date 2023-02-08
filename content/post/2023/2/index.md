---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "01/02/2023 - 03/02/2023"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: []
categories: []
date: 2023-02-03
lastmod: 2023-02-03
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

This week I started with some AWS LAB tasks. I got to create a Lab account for Omero, which he will need for school purposes. Also, another account was needed for a new employee.
Following that, I looked at an issue regarding the BI tool. Dan brought to my attention that for some projects, the project times in the database were not updating when adjusted in ZEP. However, only individual projects were affected.
It seemed like the update error was occurring rather sporadically and thus I couldn't see a concrete pattern. I then proceeded to analyze and test the SQL-Loader Lambda function locally in my development environment in more detail. When processing the CSV file, everything seemed to work correctly. Since the function seemed to be correct so far and also updates existing table entries, I then took a look at the CloudWatch logs. There I encountered an error: "IntegrityError: 1452 (23000): Cannot add or update a child row: a foreign key constraint fails", which indicates that an attempt to update or insert data in a database table failed because a foreign key constraint was violated. I then modified the Lambda function to print the rows to be inserted in the logs. After manually triggering the Lambda function, I saw that not the whole data set of the CSV file was processed. After running the function several times, it turned out that the function always takes exactly 3001 milliseconds, no matter which data set is to be updated. From this I could conclude that the Lambda function in question had too small a timeout slot. After increasing the timeout and reexecuting the update of the tables in the database, the error was eliminated.

During the rest of the time in the office, I continued working on the CloudWatch module. Furthermore, Gianluca and I joined the internal IT, as well as the Lab team. On Friday we already had the first meeting of the lab team, in which Sämi instructed us and showed us up our internal lab in more detail.

In addition, I was allowed to solve a problem reported by Horst, which concerned the docking stations of two workstations.

</p><br>
<p></p>
