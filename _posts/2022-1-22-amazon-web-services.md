---
title: "Amazon Web Services"
categories:
  - Blog
tags:
  - Cloud Native
---

<h2>Elastic Compute Cloud (Amazon EC2)</h2>

It provides scalable computing capacity in the Amazon Web Services (AWS) Cloud. Using Amazon EC2 eliminates your need to invest in hardware up front, so you can develop and deploy applications faster. You can use Amazon EC2 to launch as many or as few virtual servers as you need, configure security and networking, and manage storage. Amazon EC2 enables you to scale up or down to handle changes in requirements or spikes in popularity, reducing your need to forecast traffic.

<h2>Amazon Elastic Block Store (Amazon EBS)</h2>

It provides block level storage volumes for use with EC2 instances. EBS volumes behave like raw, unformatted block devices. You can mount these volumes as devices on your instances. EBS volumes that are attached to an instance are exposed as storage volumes that persist independently from the life of the instance. You can create a file system on top of these volumes, or use them in any way you would use a block device (such as a hard drive). You can dynamically change the configuration of a volume attached to an instance.

Amazon EBS if for data that must be quickly accessible and requires long-term persistence. EBS volumes are particularly well-suited for use as the primary storage for file systems, databases, or for any applications that require fine granular updates and access to raw, unformatted, block-level storage. Amazon EBS is well suited to both database-style applications that rely on random reads and writes, and to throughput-intensive applications that perform long, continuous reads and writes.

<h2>Amazon Virtual Private Cloud (Amazon VPC)</h2>

It enables you to launch AWS resources into a virtual network that you've defined. This virtual network closely resembles a traditional network that you'd operate in your own data center, with the benefits of using the scalable infrastructure of AWS.

The following are the key concepts for VPCs:
<ul>
<li><b>Virtual private cloud (VPC)</b>— A virtual network dedicated to your AWS account.</li>
<li><b>Subnet</b>— A range of IP addresses in your VPC.</li>
<li><b>Route table</b>— A set of rules, called routes, that are used to determine where network traffic is directed.</li>
<li><b>Internet gateway</b>— A gateway that you attach to your VPC to enable communication between resources in your VPC and the internet.</li>
<li><b>VPC endpoint</b>— Enables you to privately connect your VPC to supported AWS services and VPC endpoint services powered by PrivateLink without requiring an internet gateway, NAT device, VPN connection, or AWS Direct Connect connection. Instances in your VPC do not require public IP addresses to communicate with resources in the service. Traffic between your VPC and the other service does not leave the Amazon network. For more information, see Connect your VPC to other AWS services with AWS PrivateLink and VPC endpoints.</li>
<li><b>CIDR block</b>—Classless Inter-Domain Routing. An internet protocol address allocation and route aggregation methodology. </li>
<li><b>Egress-only internet gateways</b>- A type of internet gateway that allows an EC2 instance in a subnet to access the internet but prevents resources on the internet from initiating communication with the instance.</li>
<li><b>Carrier gateways</b>- For subnets in Wavelength Zones, this type of gateway allows inbound traffic from a telecommunication carrier network in a specific location and outbound traffic to a telecommunication carrier network and the internet.</li>
<li><b>NAT gateway</b>- A managed AWS service that allows EC2 instances in private subnets to connect to the internet, other VPCs, or on-premises networks.</li>
<li><b>NAT instance</b>- An EC2 instance in a public subnet that allows instances in private subnets to connect to the internet, other VPCs, or on-premises networks.</li>
<li><b>DHCP options sets</b>- Configuration information (such as domain name and domain name server) passed to EC2 instances when they are launched into VPC subnets.</li>
<li><b>Prefix lists</b>- A collection of CIDR blocks that can be used to configure VPC security groups, VPC route tables, and AWS Transit Gateway route tables and can be shared with other AWS accounts using Resource Access Manager (RAM).</li>
<li><b>Network ACLs</b>- An optional layer of security for your VPC that acts as a firewall for controlling traffic in and out of your subnets.</li>
</ul>

<h2>Amazon Lambda</h2>

It is a serverless compute service that runs your code in response to events and automatically manages the underlying compute resources for you. These events may include changes in state or an update, such as a user placing an item in a shopping cart on an ecommerce website. You can use AWS Lambda to extend other AWS services with custom logic, or create your own backend services that operate at AWS scale, performance, and security. AWS Lambda automatically runs code in response to multiple events, such as HTTP requests via Amazon API Gateway, modifications to objects in Amazon Simple Storage Service (Amazon S3) buckets, table updates in Amazon DynamoDB, and state transitions in AWS Step Functions.

Lambda runs your code on high availability compute infrastructure and performs all the administration of your compute resources. This includes server and operating system maintenance, capacity provisioning and automatic scaling, code and security patch deployment, and code monitoring and logging. All you need to do is supply the code.

<h2>Amazon Auto Scaling</h2>

It monitors your applications and automatically adjusts capacity to maintain predictable and stable performance at the lowest possible cost. With AWS Auto Scaling, it's easy to set up application scaling for different resources across multiple services in minutes. 
The service provides a simple and efficient user interface for creating scaling plans for resources, including Amazon EC2 instances and Spot fleets, Amazon ECS tasks, Amazon DynamoDB tables and indexes, and Amazon Aurora Replicas.

AWS Auto Scaling makes scaling easy with simple recommendations that let you optimize for performance, cost, or a balance between the two. If you already use Amazon EC2 Auto Scaling to dynamically scale Amazon EC2 instances, you can now combine it with AWS Auto Scaling to scale additional resources for other AWS services. 

<h2>AWS Identity and Access Management (IAM)</h2>

It provides fine-grained access control across all of AWS. With IAM, you can specify who can access which services and resources, and under which conditions. With IAM policies, you manage permissions to your workforce and systems to ensure least-privilege permissions.

With IAM, you can manage AWS permissions for workforce users and workloads. For workforce users, you should use AWS Single Sign-On (AWS SSO) to manage access to AWS accounts and permissions within those accounts. AWS SSO makes it easier to provision and manage IAM roles and policies across your AWS organization. For workload permissions, use IAM roles and policies, and grant only the required access for your workloads.

<h2>Amazon Simple Notification Service (Amazon SNS)</h2>

It is a fully managed messaging service for both application-to-application (A2A) and application-to-person (A2P) communication.

The A2A pub/sub functionality provides topics for high-throughput, push-based, many-to-many messaging between distributed systems, microservices, and event-driven serverless applications. Using Amazon SNS topics, your publisher systems can fanout messages to a large number of subscriber systems, including Amazon SQS queues, AWS Lambda functions, HTTPS endpoints, and Amazon Kinesis Data Firehose, for parallel processing. The A2P functionality enables you to send messages to users at scale via SMS, mobile push, and email.

<h2>Amazon Simple Queue Service (SQS)</h2>

It is a fully managed message queuing service that enables you to decouple and scale microservices, distributed systems, and serverless applications. SQS eliminates the complexity and overhead associated with managing and operating message-oriented middleware, and empowers developers to focus on differentiating work. Using SQS, you can send, store, and receive messages between software components at any volume, without losing messages or requiring other services to be available. Get started with SQS in minutes using the AWS console, Command Line Interface or SDK of your choice, and three simple commands.

SQS offers two types of message queues. Standard queues offer maximum throughput, best-effort ordering, and at-least-once delivery. SQS FIFO queues are designed to guarantee that messages are processed exactly once, in the exact order that they are sent.

<h2>Amazon Simple Storage Service (Amazon S3)</h2>

It is an object storage service offering industry-leading scalability, data availability, security, and performance. Customers of all sizes and industries can store and protect any amount of data for virtually any use case, such as data lakes, cloud-native applications, and mobile apps. With cost-effective storage classes and easy-to-use management features, you can optimize costs, organize data, and configure fine-tuned access controls to meet specific business, organizational, and compliance requirements. 

<h2>Amazon Relational Database Service (Amazon RDS)</h2>

It makes it easy to set up, operate, and scale a relational database in the cloud. It provides cost-efficient and resizable capacity while automating time-consuming administration tasks, such as hardware provisioning, database setup, patching, and backups. It frees you to focus on your applications so you can give them the fast performance, high availability, security, and compatibility they need.

Amazon RDS is available on several database instance types - optimized for memory, performance, or I/O - and provides you with six familiar database engines to choose from, including Amazon Aurora, PostgreSQL, MySQL, MariaDB, Oracle Database, and SQL Server. You can use the AWS Database Migration Service to easily migrate or replicate your existing databases to Amazon RDS.