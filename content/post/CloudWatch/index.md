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
In AWS CloudWatch, a namespace is a container for metrics. It allows to group and organize metrics so that you can more easily view and work with them. For example, you could create a namespace for metrics related to your website's performance, and another namespace for metrics related to your database. This way, you can easily view and analyze the metrics for each area of your application without having to sift through all of the metrics together.

### Standard & high resolution metrics
Amazon CloudWatch provides two different levels of metric granularity: standard resolution and high resolution.
 
Standard resolution metrics are stored at 1-minute intervals and are kept for 15 days. This type of metric is typically used for general monitoring purposes and provides a balance between cost and data detail.
 
High resolution metrics are stored at 1-second intervals and can be stored for up to 15 months. This type of metric is typically used for more detailed monitoring and troubleshooting, and provides a more detailed view of a metric's behavior over time. High resolution metrics are more expensive than standard resolution metrics.

### Alarms & Notifications
CloudWatch Alarms allow you to keep track of a single metric's value over a set time period. If the metric value goes beyond a specified threshold, the Alarm can then trigger one or more actions such as sending notifications or automatically changing resources.

A CloudWatch Notification is a notification message that gets sent to an Amazon SNS topic or an email address when the state of an alarm changes. For instance, if the alarm is activated, the Notification will be sent to inform concerned parties.


### Units & Periods  
In CloudWatch, measurement and time frame for metric monitoring are defined using Units and Periods.

Units: Units in CloudWatch identify the measurement type for a metric. For instance, the metric data for CPU utilization or network traffic could be expressed in either percent or bytes per second.

Period: The Period in CloudWatch determines the length of time in seconds over which metric data is aggregated. For example, if the period is 60 seconds, the metric data will be consolidated over 60 second intervals. The Period controls the level of detail for the metric data, with smaller periods providing more detailed data and larger periods providing less detail.

</p><br>
<p></p>
