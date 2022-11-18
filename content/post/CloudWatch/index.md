---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "Tasks AWS CloudWatch"
subtitle: ""
summary: "Here you can find the tasks associated to the CloudWatch module."
authors: [Xavier Jeiziner]
tags: [PiBS]
categories: []
date: 2022-11-16
lastmod: 2022-11-16
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: Photo by C. Dustin on Unsplash
  focal_point: Top
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---
 ## Important concepts & definitions in AWS CloudWatch
 ### Standard metrics & custom metrics
 A metric represents a time-ordered set of data points that are accessible via CloudWatch. You can think of a metric as a variable that represents data points. An example of this can be the error count and success rate of a lambda function. With metrics you can get an idea about the performance and other measurable aspects of your system. Metrics are aggregable from many different AWS-Services.

 ![Standard metric for a lambda function](success-lambda.jpg "<b>Standard metric for a lambda function | </b>Screenshot from LAB-Account")

 A standard metric is grouped by the service name and is created automatically from scratch by AWS. The metric appears only if the service has been used in the last 15 months. They are graphically displayed by plots and are reachable via the AWS CLI or API. An example could be the CPU usage of an EC2 instance or as mentioned above the Lambda failure rate.

 As the name suggests, the user can create custom metrics for an individual use case. An example of this could be a monitoring system that records how many drivers are driving without daytime running lights on a certain section of road during the day and visualizes this by summing it up in a CloudWatch metric.

 ### Namespaces

 ### Standard & High Resolution

 ### Alarms & Notifications

 ### Units & Periods  

</p><br>
<p></p>
