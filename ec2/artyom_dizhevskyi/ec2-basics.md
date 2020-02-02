# EC2

**Amazon Elastic Compute Cloud (Amazon EC2)** is a web service that provides secure, resizable compute capacity in the cloud. It is designed to make web-scale cloud computing easier for developers. Amazon EC2’s simple web service interface allows you to obtain and configure capacity with minimal friction. It provides you with complete control of your computing resources and lets you run on Amazon’s proven computing environment.
<br />
<br />
### EC2 types:

------------
**Instance** - most popular type. On demand server instance with hourly pay model. Suitable for all tasks general purpose tasks.

**Spot** - let you take advantage of unused EC2 capacity in the AWS cloud. Spot Instances are available at up to a 90% discount compared to On-Demand prices. Hourly pricing model. Works like stocks market: less demand - less price and vice versa. You can set a bid price and if the spot price is less than yours, you will receive the instance(s) you need. If the spot price has risen higher than the bid you set, then all your spot servers will be automaticaly terminated and payment for the last hour of terminated spot instance won't be charged.

**Reserved Instances** - contract based instances with term from 1 month to 3 years. Can be payed by 3 ways: No Upfront - all sum at the end of contract; Partial Upfront - pay by parts; All Upfront - all sum right away (Most cheepest way).

**Scheduled Reserved Instances** -  almost the same as a **Reserved Instances** but can be purchaised for a smaller term with recurring launches (daily, weekly or monthly).  They are available in the following Regions: US East (N. Virginia), US West (Oregon), and Europe (Ireland).

**Dedicated hosts** - physical server. EC2 types above will work as virtual servers, but dedicated server gives you much more control and elasticity. You can build your own virtual instances clusters on it.
<br />
<br />
### EC Instance types

------------
Instance type naming schema:
**type(+generation).(multiplier+)sizetype**

![](https://imgur.com/LRLKOWT.png)

#### Types:
**A, T, M** - General purpose

**C** - Comptue Optimized

**R, X, High Memory, z1d** - Memory Optimized

**P, Inf, G, F** - Accelerated Computing (GPU Optimized)

**I, D, H** - Storage Optimized
<br />
<br />

#### Size types:
**micro, nano, small, medium, large, xlarge(extra large)**

**metal** - special size type with physical CPUs

<br />

#### To change the type of your instance, you just need to stop(not terminate!) it, change the type and start it again.