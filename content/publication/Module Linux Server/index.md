---
title: "Module Server Administration and Networks with Linux"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here 
# and it will be replaced with their full name and linked to their profile.
authors:
- admin

# Author notes (optional)
author_notes: ""

date: "2021-11-17"
doi: ""

# Schedule page publish date (NOT publication's date).
publishDate: ""

# Publication type.
# Legend: 0 = Uncategorized; 1 = Conference paper; 2 = Journal article;
# 3 = Preprint / Working Paper; 4 = Report; 5 = Book; 6 = Book section;t
# 7 = Thesis; 8 = Patent
publication_types: ["0"]

# Publication name and optional abbreviated publication name.
publication: ""
publication_short: ""

abstract: ""

# Summary. An optional shortened abstract.
summary: Beside the the school we have to complete different modules in our company. The third topic is about server administration and networks with Linux.

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ''
url_code: ''
url_dataset: ''
url_poster: ''
url_project: ''
url_slides: ''
url_source: ''
url_video: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: 'Image credit: [**Unsplash: Teng Yuhong**](https://unsplash.com/photos/qMehmIyaXvY)'
  focal_point: ""
  preview_only: false

# Associated Projects (optional).
#   Associate this publication with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `internal-project` references `content/project/internal-project/index.md`.
#   Otherwise, set `projects: []`.
projects: []

# Slides (optional).
#   Associate this publication with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides: "example"` references `content/slides/example/index.md`.
#   Otherwise, set `slides: ""`.
slides: ""
---
## {{< hl >}}<b>Get Started with Linux</b>{{< /hl >}}<br>
In this module I will learn how to administrate servers and networks with Linux. Here you will find several tasks about the topic.<br>
> Write a definition for virtualization.

Virtualization allows multiple resources or environments to be configured on a single hardware system. The different environments and resources can be referred to as virtual machines, which act independently of each other. Therefore you need a hypervisor. The hypervisor is software that manages the various VM containers. It divides the machine resources optimally between the different VMs.<br>

> Complete the definition with advantages and disadvantages of virtualization.

`Advantages of virtualization:`<br>
- Exploiting the potential of your own hardware
- Cost savings / Energy saving, because less hardware is needed
- more flexibility
- easier upgrade and downgrade of used / unused extensions
- Through virtualization, custom labs can be implemented to test environments in advance.

`Disadvantages of virtualization:`<br>
- In the event of a hardware failure, all virtual machines are affected.
- Higher response times with many VM's on one hardware.
- Performance degradation as the hypervisor also requires resources
