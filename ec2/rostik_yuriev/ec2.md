## What is EC2

**Amazon Elastic Compute Cloud(Amazon EC2)** - is a web service that provides scalable computing resources in the cloud. The service allows you to simplify the process for developers of computing on the Internet.

<br />

## What is cloud computing?

This is the provision of computing services (including servers, storage, databases, networks, software, analytics and data mining) via the Internet (“cloud”)

<br />

## Advantages

`Expenses` - Cloud computing avoids the capital cost of acquiring hardware and software, setting up and operating local data centers

`Global scale` - cloud computing services include scalability

`Performance` - cloud computing services regularly updated to the latest generation of fast and efficient computing equipment

`Security` - cloud service providers increase security by helping protect data, applications, and infrastructure from potential threats

`Speed` - large amounts of computing resources can be prepared in a few minutes, usually in just a few clicks

`Reliability` - Cloud computing makes data backup, disaster recovery, and business continuity easier and less costly

<br /><br />

# Regions

is the physical location where our data centers are located

<br />

## All existing regions

![](/assets/images/aws/regions_aws.png)

<br />

## Which region to choose?

You need to choose a region based on the needs of your specific application.
It may make sense to store data in a region that...

- located close to your customers, data centers or other AWS resources, to reduce data access latency

- removed from your other nodes and systems for geographic redundancy and disaster recovery

- allows you to meet certain legal and regulatory requirements

- reduces the cost of machine hours and data storage. For economic reasons, you can choose a less expensive region

<br /><br />

# Instance

**An EC2 instance** - is a virtual server in Amazon's Elastic Compute Cloud, for running applications on the Amazon Web Services infrastructure

<br />

##kinds of servers

 **on Demand** - the most common type of server (when needed for several hours, for example, turned on for 2 hours and then immediately deleted) payment is done hourly. If you turned on the server for 5 minutes and then turned it off, then you will pay for an hour

 **spot request** - when on demand servers are not taken so that they are not idle, they can reduce the price.
  they are needed for works that do not require the importance of storing information on the servers themselves, that is, they do some work and no matter what happens to the data

 **reserved instances** - usually take for long periods from 1 to a maximum of 3 years, this is a very cheap option compared to ondemand (70% cheaper)

 **scheduled instances** - there is not in all regions, take for a short period of time a day a week a month. cheaper option compared to ondemand

 **dedicated hosts** - when the whole server (not a piece of processor and memory) belongs to you. needed for leasing

<br />

##types of servers

types include how many processors, memory, disks

# Types of EC2 Instances

- General Purpose Instances - **T, M** - (generic type, free)


- Computer Optimized Instances - **C** - (bigger and more powerful processors)

- Memory Optimized Instances - **X, R** - (memory db)

- Accelerated Computing Instances - **P, G, F** - (powerful graphics cards)

- Storage Optimized Instances - **I**
- Dense Storage Instances - **D**
  (for databases, when needs to connect many hard disks)

## Type hard disk
- *general purpose ssd gp2* standard (10.000 iops(input output per second))
- *provisioned iops ssd io1* more powerful (20.000 iops)
- *magnetic* - the cheapest and weakest hard disk
- *throughput optimized hdd st1*
- *cold hdd*

https://mindmajix.com/aws-ec2-instance-types

<br /><br />

## Changing the Instance Type

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-resize.html

<br /><br />

# AMI

AMI - the type of virtual device that is used to create the virtual machine.

the virtual machine on which all the software is stored, you can use it to start new instances

https://ru.bmstu.wiki/AMI_(Amazon_Machine_Image)

<br /><br />

# Tags

Amazon Web Services allows customers to assign metadata to their AWS resources in the form of tags. Each tag is a simple label consisting of a customer-defined key and an optional value that can make it easier to manage, search for, and filter resources. Also it is aws best practices

For more info - https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/Using_Tags.html

<br />


#Key pairs

Amazon AWS uses keys to encrypt and decrypt login information. At the basic level, a sender uses a public key to encrypt data, which its receiver then decrypts using another private key. These two keys, public and private, are known as a key pair. You need a key pair to be able to connect to your instances

##How to create Key pair for EC2

- Open the Amazon EC2 console at https://console.aws.amazon.com/ec2/.

- In the navigation pane, choose *Key Pairs*.

- Choose Create *key pair*.

- For *Name*, enter a descriptive name for the key pair.

- For *File format*, choose the format in which to save the private key. To save the private key in a format that can be used with OpenSSH, choose *pem*. To save the private key in a format that can be used with PuTTY, choose *ppk*.

- Choose *Create key pair*.

<br />

for more info(different contents of key pairs and manage it) see -  https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html

<br /><br />

#Instance creation example

  https://aws.amazon.com/ru/getting-started/tutorials/launch-a-virtual-machine/


<br /><br />

## The end

<br /><br />
