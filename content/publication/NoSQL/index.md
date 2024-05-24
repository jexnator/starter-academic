---
title: "Introduction to NoSQL"

# Authors
# If you created a profile for a user (e.g. the default `admin` user), write the username (folder name) here
# and it will be replaced with their full name and linked to their profile.
authors:
  - admin

# Author notes (optional)
author_notes: ""

date: "2024-05-23"
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
summary: Beside the the school we have to complete different modules in our company. This publication is about NoSQL.

tags: [PiBS]

# Display this page in the Featured widget?
featured: true

# Custom links (uncomment lines below)
# links:
# - name: Custom Link
#   url: http://example.org

url_pdf: ""
url_code: ""
url_dataset: ""
url_poster: ""
url_project: ""
url_slides: ""
url_source: ""
url_video: ""

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: "Image credit: [**Unsplash: C Dustin**](https://unsplash.com/photos/K-Iog-Bqf8E)"
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

{{< toc >}}

# {{< hl >}}<b>NoSQL</b>{{< /hl >}}<br>

## {{< hl >}}<b>Difference Between Distributed and Centralized Systems</b>{{< /hl >}}<br>

### # {{< hl >}}Centralized Systems</b>{{< /hl >}}<br>

Centralized systems operate with a single node (server) handling all tasks. Here are the key characteristics:

1. **Single Node Operation**: One node executes the same task, making the system simpler but less scalable.
2. **Data Storage**: Related data is always stored on the same node, ensuring easy access but limiting data handling capacity.
3. **ACID Properties**: These systems adhere to the ACID (Atomicity, Consistency, Isolation, Durability) properties, ensuring reliable transactions.
4. **Independence of Nodes**: No inter-node management is required, as nodes operate independently.
5. **Limitations with Big Data**: Centralized systems struggle with handling large volumes of data.
6. **Performance Constraints**: Performance tuning is limited, and the system requires more time to process tasks because:
   - All data must be scanned due to the absence of partitioning.
   - Access management becomes increasingly complex as data and users grow.

### # {{< hl >}}Distributed Systems</b>{{< /hl >}}<br>

Distributed systems leverage multiple nodes to perform tasks. Key features include:

1. **Multiple Node Operation**: Tasks are distributed across several nodes, enhancing scalability and fault tolerance.
2. **Distributed Data Storage**: Related data can be scattered across multiple nodes, allowing for better data management and access speed.
3. **CAP/PACELC Theorem**: These systems follow the CAP (Consistency, Availability, Partition Tolerance) or PACELC (Partition tolerance, Availability, Consistency Else Latency, Consistency) theorems, balancing trade-offs in performance and reliability.
4. **Management Requirements**: Requires sophisticated management for consistency, replication, and fault tolerance.
5. **Handling Big Data**: Capable of managing large data volumes effectively.
6. **Performance Optimization**: Performance can be fine-tuned through CAP trade-offs, offering flexibility in system behavior.
7. **Efficiency in Task Fulfillment**: Distributed systems require less time to complete tasks because:
   - Data is sharded and replicated across multiple servers, facilitating faster access and processing.
   - Access management can be simplified, depending on the consistency model chosen.

## {{< hl >}}<b>Scaling</b>{{< /hl >}}<br>

### {{< hl >}}<b>Vertical Scaling</b>{{< /hl >}}<br>

Vertical scaling involves enhancing the capacity of a single node by upgrading its hardware. Key points include:

1. **Applicability**: Particularly effective for centralized systems but can also be applied to distributed systems.
2. **Hardware Limitations**: There is a finite limit to vertical scaling, constrained by the most advanced available hardware.
3. **Performance Boost**: Improves performance by increasing the node’s processing power, memory, or storage.

### {{< hl >}}<b>Horizontal Scaling</b>{{< /hl >}}<br>

Horizontal scaling involves adding more nodes to the system to distribute the workload. Important aspects are:

1. **Distributed Systems**: Primarily used in distributed computing environments.
2. **Scalability**: There is no inherent limit to horizontal scaling; additional nodes can always be added.
3. **Fault Tolerance and Load Balancing**: Enhances system reliability and efficiency by spreading the load across multiple nodes.

### {{< hl >}}<b>Combined Scaling</b>{{< /hl >}}<br>

Both vertical and horizontal scaling can be used together to optimize performance:

1. **Enhanced Flexibility**: Combining both scaling methods allows for greater flexibility and optimization.
2. **Comprehensive Performance Improvement**: Utilizing both strategies can address the limitations of each, providing a more robust and scalable system.

![Scaling](scaling-v-h.png "Scaling")

## {{< hl >}}<b>NoSQL Databases</b>{{< /hl >}}<br>

### {{< hl >}}<b>Definition</b>{{< /hl >}}<br>

NoSQL stands for "Not Only SQL." This designation highlights that while NoSQL databases may include query languages, they are distinct from traditional SQL databases. Key characteristics include:

1. **Non-relational Structure**: NoSQL databases are schemaless and designed to avoid join operations.
2. **Designed for Distribution**: Although they can be hosted as single-node systems, they are optimized for multi-node (distributed) computation.
3. **Horizontal Scaling**: NoSQL databases inherently support horizontal scaling, enabling them to handle large-scale data efficiently.
4. **Broad Categorization**: Any database that does not follow a relational model is categorized as NoSQL.

### {{< hl >}}<b>Performance and Use Cases</b>{{< /hl >}}<br>

NoSQL databases offer performance advantages in specific scenarios due to their consistency models and design optimizations:

1. **Read-Operations and Small Transactions**: They are highly performant for read-heavy operations and small transactions.
2. **Big Data and Data Analytics**: Optimized for fast reading of huge datasets, making them ideal for big data computation and analytics.
3. **Business Applications**: Less suitable for applications requiring complex relations with numerous write operations, as they are not optimized for such use cases.

![Comparison SQL vs. NoSQL](sql-nosql.png "Scaling")

## {{< hl >}}<b>CAP-Theorem</b>{{< /hl >}}<br>

### {{< hl >}}<b>Definition</b>{{< /hl >}}<br>

The CAP-Theorem, relevant for NoSQL databases, provides a framework analogous to the ACID theorem for relational databases. ACID properties are not applicable to NoSQL databases, necessitating the use of the CAP theorem. CAP stands for:

1. **Consistency**: Ensures that if one node has updated data (e.g., version v2), all other nodes should reflect this updated version.
2. **Availability**: The system must always be operational, minimizing downtime and locks.
3. **Partition Tolerance**: The system should continue to function even if parts of the network fail.

### {{< hl >}}<b>Theoretical Limitations</b>{{< /hl >}}<br>

In theory, a distributed system can only satisfy two of the three CAP properties simultaneously:

1. **Consistency and Partition Tolerance (CP)**:

   - The system maintains consistent data across nodes by locking nodes to ensure the same data version on all nodes.
   - This approach sacrifices availability because multiple nodes may become unavailable during data synchronization.

2. **Availability and Partition Tolerance (AP)**:

   - The system remains operational and accessible on all nodes, ensuring minimal downtime.
   - This approach sacrifices consistency, as there is no guarantee that all nodes will have the most recent data version.

3. **Consistency and Availability (CA)**:
   - This combination is only feasible in centralized systems.
   - For distributed systems, achieving both consistency and availability without partition tolerance is impossible.

![CAP](cap.png "CAP-Theorem")

</p><br>
<p></p>
---
