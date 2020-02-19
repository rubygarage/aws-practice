# EC2

**Amazon Elastic Compute Cloud (Amazon EC2)** is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.

<br />

### EC2 launch types:

TL;DR
- **On Demand Instances:** short workload, predictable pricing
- **Reserved Instances:** long workloads (>= 1 year)
- **Convertible Reserved Instances:** long workloads with flexible instances
- **Scheduled Reserved Instances:** launch within time window you reserve
- **Spot Instances:** short workloads, for cheap, can lose instances
- **Dedicated Instances:** no other customers will share your hardware
- **Dedicated Hosts:** book an entire physical server, control instance placement

------------
 **On Demand Instance** - most popular type. On demand server instance with hourly payment model. Suitable for all general purpose tasks.

**Spot** - let you take advantage of unused EC2 capacity in the AWS cloud. Spot Instances are available at up to a 90% discount compared to On-Demand prices. Hourly pricing model. Works like stocks market: less demand - less price and vice versa. You can set a bid price and if the spot price is less than yours, you will receive the instance(s) you need. If the spot price has risen higher than the bid you set, then all your spot servers will reclaimed(terminated) with a 2 minute notification warning and payment for the last hour of terminated spot instance won't be charged.

## Reserved:

- **Reserved Instances** - contract based instances with term from 1 month to 3 years. Can be payed by 3 ways: No Upfront - all sum at the end of contract; Partial Upfront - pay by parts; All Upfront - all sum right away (Most cheepest way). Can be much more beneficial in long term (Up to 75% discount compared to On-demand) than on demand instance with the same term!

- **Scheduled Reserved Instances** -  almost the same as a **Reserved Instances** but can be purchaised for a smaller term with recurring launches (daily, weekly or monthly).  They are available in the following Regions: US East (N. Virginia), US West (Oregon), and Europe (Ireland).

- **Convertible Reserved Instances:** - Can change the EC2 instance type. Up to 54% discount

## Dedicated:

- **Dedicated hosts** - physical dedicated EC2 server for your use. EC2 types above will work as virtual servers, but dedicated server gives you much more control and elasticity. You can build your own virtual instances cluster on it. Allocated for your account for a 3 year period reservation. Visibility into the underlying sockets/physical cores of the hardware

- **Dedicated instances** - physical instances running on hardware that’s dedicated to you. May share hardware with other instances in same account. No control over instance placement (can move hardware after Stop / Start)

<br />

## EC Instance types

------------
Instance types naming schema:
**type(+generation).(multiplier+)sizetype**

![](https://imgur.com/LRLKOWT.png)

### Types:
**A, T, M** - General purpose

**C** - Compute Optimized

**R, X, High Memory, z1d** - Memory Optimized

**P, Inf, G, F** - Accelerated Computing (GPU Optimized)

**I, D, H** - Storage Optimized

<br />

### Size types:
**micro, nano, small, medium, large, xlarge(extra large)**

**metal** - special size type with physical CPUs

<br />

#### To change the type of your instance, you just need to stop(not terminate!) it, change the type and start it again.

<br />

# Burstable Instances (T2/T3)

AWS has the concept of burstable instances (T2 machines)
- Burst means that overall, the instance has OK CPU performance.
- When the machine needs to process something unexpected (a spike in load for example), it can burst, and CPU can be VERY good.
- If the machine bursts, it utilizes “burst credits”
- If all the credits are gone, the CPU becomes BAD
- If the machine stops bursting, credits are accumulated over time
- Burstable instances can be amazing to handle unexpected traffic and
getting the insurance that it will be handled correctly
- If your instance consistently runs low on credit, you need to move to a
different kind of non-burstable instance (all the ones described before).

# T2/T3 Unlimited (unlimited burst credit balance)
#### You pay extra money if you go over your credit balance, but you don’t lose in performance.

## **Important:** T3 instances launch as unlimited by default.

<br />

## ============ Useful links ============
https://aws.amazon.com/ec2/instance-types/

https://www.ec2instances.info/

https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/burstable-credits-baseline-concepts.html

https://aws.amazon.com/blogs/aws/new-t2-unlimited-going-beyond-the-burst-with-high-performance/

https://aws.amazon.com/ec2/instance-types/t3/