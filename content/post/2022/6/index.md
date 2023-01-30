---
# Documentation: https://wowchemy.com/docs/managing-content/

title: "20/09 - 07/10/2022"
subtitle: ""
summary: "Trainee diary"
authors: [Xavier Jeiziner]
tags: [PiBS]
categories: []
date: 2022-10-07
lastmod: 2022-10-07
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: Photo by Erwan Hesry on Unsplash
  focal_point: Top
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

The last two weeks I have been preparing for exams.
This week I worked in between on an algorithm to find the median in an unsorted array in linear time.
The main goal of this week was to find out why a specific lambda function takes so long and has a high cost. It turned out that it is not the lambda function itself that is to blame, but that the request via the soap wastes a lot of time. Nevertheless it has to be said that the dataset is quite large compared to the other datasets that are obtained in the other lambdas.
This means that the function also requires comparatively more memory. By increasing the working memory, the Lambda function is now about half faster.

At this point I would like to thank Dino and Leo for their support and helpful inputs.

I then recalculated the cost of the Lambda using the "AWS Lambda Pricing Calculator". Despite the long duration, I found that this was not the cost driver as Dan initially feared. After further analysis, I came to the conclusion that the high costs in the Lambda area were due to the "AWS Lambda - Provisioned Concurrency" feature. In the account where the BI tool is currently still running, there was an unneeded Lambda function somewhere that had activated this feature and was wasting money unnecessarily.
This feature keeps the container of the required Lambda function warm, so that it can be executed within the shortest possible time when an event occurs. This way the container is always running. Normally the container is booted as soon as the lambda receives an event, which takes a certain instantiation time, which can be eliminated by this.

Next week I will test my version written in CDK with Python and see if everything works as desired.


</p><br>
<p></p>