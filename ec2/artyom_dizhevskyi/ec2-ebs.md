# EBS

**Amazon Elastic Block Store (EBS)** is an easy to use, high performance block storage service designed for use with Amazon Elastic Compute Cloud (EC2) for both throughput and transaction intensive workloads at any scale. A broad range of workloads, such as relational and non-relational databases, enterprise applications, containerized applications, big data analytics engines, file systems, and media workflows are widely deployed on Amazon EBS.

#### Types:

------------
#### **Root-Boot discs:**
**General purpose SSD (GP2)** - up to 10.000 *iops.<br />
(Boot volumes, low-latency interactive apps, dev & test)

**Provisioned IOPS SSD (IO1)** - up to 20.000 iops. **Most powerful disk type.**<br />
(I/O-intensive NoSQL and relational databases)

**Magnetic** - standart HDD

<br />

#### **Additional types. (Not available as root-boot):**
**Throughput Optimized HDD (ST1)** - enchanced HDD. For frequently accessed workloads.<br />
(Big data, data warehouses, log processing)

**Cold HDD (SC1)** - lowest cost HDD. For less frequently accessed workloads.<br />(Colder data requiring fewer scans per day)


*iops - input/output operations per second