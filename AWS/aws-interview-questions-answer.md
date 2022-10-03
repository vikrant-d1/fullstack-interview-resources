# AWS-Interview-Questions
### 1. What is AWS?

Amazon Web Services (AWS) is a platform that offers safe cloud services, data storage facilities, computing platforms, content delivery, and various other associated services to the users.

### 2. What are the various types of AWS cloud products?
There are mainly three kinds of cloud service types that AWS products offer. These are:
- **Computing:** Auto-scaling, EC2, Lightsat, Elastic Beanstalk, and Lambda
- **Storage:** S3, Elastic File System, Elastic Block Storage, and Glacier
- **Networking:** VPC, Route53, and Amazon CloudFront

### 3. What is Auto-scaling?

AWS auto-scaling helps in monitoring business applications and adjusting their capacity as needed to keep the performance steady and predictable. It also helps in achieving this in a cost-effective manner. Moreover, with AWS auto-scaling, businesses can scale applications across multiple resources in just a few minutes.
### 4. Is there a difference between region and availability zone?

Yes. Regions are different geographical locations like the United States-West or North California, and Asia South or Mumbai. An availability zone is a part of these regions, and are mostly isolated zones that can replicate itself when the need arises.
### 5. What do you understand by geo-targeting in CloudFront?

Geo-targeting in the CloudFront supports the creation of customized content for a  target audience as suggested by demand and the needs of a specific geographical area. This helps businesses showcase their personalized content to the target audience in different geographic locations without changing its URL.
### 6. What are the steps involved in CloudFront?

There are four steps involved in CloudFront. These are:

    Step 1: Creating a CloudFormation template in YAML or JSON format
    Step 2: Saving the code in an S3 bucket so that it serves the repository for the code
    Step 3: Using the AWS CloudFormation to call the bucket and thereby creating a new stack on the template
    Step 4: CloudFormation reads the file and thus understands the services required that are called along with their order details, relationships with services and associated provisions

### 7. Which AWS tools help you recognize that you’re paying more than required?

There are four such tools available in AWS. These are:

    Checking the top service table
    AWS budgets
    Cost allocation tags
    Cost explorer

### 8. What is S3 in AWS?

S3 is referred to as Simple Storage Service. It is used to store and retrieve data of any amount at any time from anywhere in the world using the web. To use this service the payment model developed is “Pay As You Go”.
### 9. What is AMI?

Amazon Machine Image is a template that offers the information required to launch an instance that acts as a copy of AMI running as a virtual server in the cloud. The information provided is about the operating system, applications and the application server itself. Many instances can be launched at one time from different AMIs as per your instructions.

### 10. What is the relation between AMI and Instance?

Instances can be launched by AMIs. One AMI can launch as many instances as required. An instance type defines the hardware of the host computer including information about computers and its memory abilities. After launching an instance, it works as a traditional host and could be interacted with as with any other computer.
### 11. What are the inclusions in AMI?

There are three inclusions in AMI which include the following:

    Template for the root volume for the instance
    Block device mapping that helps in determining the volumes after attaching to the instance after launch
    Launch permissions that help decide which AWS account can take the AMI for launching instances

### 12. Can we send a request to Amazon S3?

Yes, we can send a request to Amazon S3 by using the REST API or the AWS SDK wrapper libraries which wrap the underlying Amazon S3 REST API.
### 13. What are the main differences between EC2 and S3?

The main differences between EC2 and S3 are stated under.

EC2
S3

A cloud web service

A data storage system

Used for hosting the web application
	

Used for storing data

Works as a huge computer machine
	

It is a REST interface

It can either run LINUX or Windows and could also handle PHP, Python, Apache and various other kinds of databases
	

It applies secure authentication keys such as HMAC-SHA1
### 14. Can buckets be created in AWS accounts?

Yes, buckets can be created in AWS accounts. By default up to 100 buckets can be created in the AWS account.
### 15. What is a T2 Instance?

A T2 instance is specifically designed to offer moderate baseline performance and the ability to burst into higher performance as demanded by the workload.
### 16. What are the different kinds of instances?

The different kinds of instances include the following.

    Accelerated Computing Instance
    Memory-Optimized Instance
    Storage Optimized Instance
    Computer Optimized Instance
    General Purpose Instance

### 17. Does Amazon VPC support the property of broadcast or multicast?

No, Amazon VPC does not support the property of broadcast or multicast.
### 18. Can we create Elastic IPs in AWS?

Yes, we can create Elastic IPs in AWS. About 5 VPC Elastic IP addresses are allowed under each AWS account.
### 19. What is a default storage class in S3?

The default storage class in S3 is referred to as the Standard frequently accessed.
### 20. What are roles in AWS?

Roles in AWS are used to provide permission to the entities that can be trusted within the AWS account. They are similar to users and do not require the creation of a username and password to work along with various other resources in AWS.
### 21. What are edge locations in AWS?

Edge locations in AWS are data centers that deliver as low a latency as possible, i.e., these data centers are physically close to the client. When a user tries to access content, the searches automatically search in the edge location for the fastest reponses.
### 22. What is VPC?

The full form of VPC is Virtual Private Cloud. VPC helps in customizing the network configuration process. It acts as a network that is logically isolated from various other networks in the cloud. VPC allows the users to have an IP address range, security groups, subnet and internet gateways.
### 23. What is a Snowball?

A Snowball in AWS is a data transport option. It uses secure devices to transfer a large amount of data in and out of the cloud. Snowball can be used for the transfer of massive data from one place to another, and helps reduce networking costs.
### 24. What is Redshift?

Redshift is a fast and powerful data warehouse product that performs data analytics and large scale database migrations. Each Redshift data warehouse contains a set of nodes, arranged in what is called a cluster. Clients can use uncommonly fast querying results to gain insights from large volumes of data. The most common applications are real-time analytics, business intelligence, and log analysis.
### 25. What is a Subnet?

Subnets are large sections of IP Address which can be divided into chunks. 200 subnets can exist per VPC.
### 26. What is SQS?

Simple Queues Services offers a distributed queuing service that acts as a mediator for two controllers.
### 27. What is SimpleDB?

SimpleDB is the data repository structure record that supports data doubts and index S3, and EC2.
### 28. What is Amazon ElastiCache?

Amazon ElastiCache is a web service that helps in easy deployment, scaling, and storing of data in the cloud.
### 29. What is AWS Lambda?

AWS Lambda is a computing service offered by Amazon to run code in the AWS cloud without managing the servers.
### 30. What is Amazon EMR?

Amazon EMR is a survived cluster stage that helps in interpreting the working of the different data structures before the intimation. The various components of Amazon EMR are Apache Hadoop, Apache Spark, Apache Hive and various others. They help in investigating a large amount of data, prepare data analytic goals and market intellect workloads using open-source designs.
### 31. What is the difference between stopping and terminating an instance?

Both stopping and terminating are states in an EC2 instance:

    Stopping: As soon as an instance is stopped, it performs a normal shutdown and transitions to a stopped state. You can start the instance at a later time and all of its Amazon EBS volumes remain attached. While the instance is in a stopped state, no additional instance hours are incurred.
    Terminating: As soon as an instance is terminated, it performs a normal shutdown and transitions to the terminated state. The attached Amazon EBS volumes are deleted, save for the case when the volume’s deleteOnTermination attribute is set to false. As the instance itself is deleted, it is not possible to start the instance again at some later time.

Advanced AWS Interview Questions
### 32. How will you use the processor state control feature available on the c4.8xlarge instance?

The processor state control has 2 states, namely:

    The C State: Represents the sleep state. Varies from c0 to c6, where c6 is the deepest sleep state for a processor.
    The P State: Represents the performance state. Varies from p0 to p15, where p15 is the lowest possible frequency.

A processor has multiple cores, and each of them requires thermal headroom for gaining a boost in performance. Hence, the temperature needs to be kept at an optimal level so that the cores can perform at their highest.

When a core is put into the sleep state then it results in a reduction of the overall temperature of the processor. This gives an opportunity to other cores for giving out a better performance. Hence, a strategy can be devised by properly putting some cores to sleep and others in a performance state to get an overall performance boost from the processor.

Instances like the c4.8xlarge allow customizing the C and P states for customizing the processor performance according to the workload.
33. Which instance type can be used for deploying a 4 node cluster of Hadoop in AWS?

While the c4.8xlarge instance will be preferred for the master machine, the i2.large instance seems fit for the slave machine. Another way is to launch the Amazon EMR instance that automatically configures the servers.

Hence, you need not deal with manually configuring the instance and installing Hadoop cluster while using Amazon EMR instance. Simply dump the data to be processed in S3. EMR picks it up from there, processes the same, and then dumps it back into S3.
### 34. Can you differentiate between a Spot instance and an On-Demand instance?

Both spot instances and on-demand instances are pricing models. A spot instance allows customers to purchase compute capacity with no upfront commitment. Moreover, the hourly rates for a spot instance are usually lower than what has been set for on-demand instances.

The bidding price for a spot instance is known as the spot price. It fluctuates based on the supply and demand for spot instances. In case the spot price gets higher than a customer’s maximum specified price, the EC2 instance will shut down automatically.
### 35. What are some of the best practices to improve security in Amazon EC2?

The following are some of the best practices to improve security in Amazon EC2:

    Allow only trusted hosts or networks to access ports on your instance
    Control access to the AWS resources with AWS Identity and Access Management (IAM)
    Disable password-based logins for instances launched from the AMI
    Frequently review rules in the security groups

### 36. Is it possible to use Amazon S3 with EC2 instances? Please elaborate.

Yes, it is possible to use Amazon S3 with EC2 instances. It can be used for instances with root devices backed by the local instance storage. Amazon provides an array of tools to load the AMIs into Amazon S3 and to move them amongst Amazon S3 and Amazon EC2 instances.

With Amazon S3, AWS developers enjoy accessing the same highly fast, reliable, inexpensive, and scalable data storage infrastructure used by Amazon to operate its very own global network of websites and services.
### 37. How will you speed up data transfer in Amazon Snowball?

 Data transfer in Amazon Snowball can be enhanced by:

    Copying from different workstations to the same snowball
    Creating a batch of small files or transferring large files for reducing the encryption overhead
    Eliminating needless hops
    Performing multiple copy operations simultaneously

### 38. Can you explain the difference between Amazon RDS and Amazon DynamoDB?

Amazon RDS is a database management service for relational databases. It allows automating several relational database-related operations like backup, patching, and upgrading. The service deals with structured data only.

Amazon DynamoDB, on the other hand, is a NoSQL database service. Contrary to the Amazon RDS, it deals with unstructured data only. 

Read our guide on NoSQL vs SQL to learn about the important differences between SQL and NoSQL databases.
### 39. Which AWS services suit the real-time analysis of eCommerce data?

DynamoDB is an appropriate choice for collecting eCommerce data as it is an unstructured form of data. Real-time analysis of the collected eCommerce data can be carried out using Amazon Redshift.
### 40. What happens to the backups and DB Snapshots if a DB instance is deleted?

While deleting a DB instance, there is an option for creating a final DB snapshot. It can be used later for restoring the database.

The Amazon RDS retains the user-created DB snapshot alongside other manually-created DB snapshots once the instance is deleted. All automated backups are deleted along with the instance.
### 41. How will you load data to Amazon Redshift from different data sources, such as Amazon EC2, DynamoDB, and Amazon RDS?

There are two ways of loading data to Amazon Redshift from different data sources, namely:

    Using the AWS Data Pipeline: Offers high performance, fault-tolerance, and a reliable way of loading data from a range of AWS data sources. It allows specifying the data source, data transformations, and then executing a pre-written import script for loading data
    Using the COPY command: Load data in parallel directly from Amazon DynamoDB, Amazon EMR, or any other SSH-enabled host

### 42. How does elasticity differ from scalability?

The ability of a system to handle an increase in the workload by simply adding hardware resources when demand rises, and rolling back scaled resources when there’s no demand, is known as elasticity.

Scalability, on the other hand, is the ability of a system to increase the hardware resources for handling an increase in demand. It can be achieved by either increasing the hardware specs or increasing the number of processing nodes.
### 43. What is connection draining?

Connection draining is responsible for re-routing the traffic from instances to other, available instances. This happens for instances that are either due to be updated or those that have failed a health check. It is an ELB service that continuously monitors the health of instances.
### 44. Suppose a user has set up an Auto Scaling group but the group fails to launch a single instance for over 24 hours. In this scenario, what happens to Auto-scaling?

In such a case, Auto-scaling will suspend the scaling process. The Auto-scaling feature allows suspending and resuming one or many processes belonging to the Auto-scaling group.

The feature is extremely useful when a web application needs to be investigated for a configuration or some other issue.
### 45. How will you transfer an existing domain name registration to Amazon Route 53 without disrupting the extant web traffic?

    Get a list of DNS record data for the domain name. It is typically available in the form of a zone file that can be gained from the extant DNS provider.
    After receiving the DNS record data, use the Route 53 Management Console or the simple web-services interface for creating a hosted zone for storing the DNS records for the domain name and continue the transfer process. Here, you can also include other non-essential steps such as updating nameservers for the domain name to the ones associated with the hosted zone.
    Contact the registrar with whom you have registered the domain name and then follow the transfer process. The DNS queries will start getting answered as soon as the registrar propagates the new name server delegations.

### 46. What are the ideal cases for using the Classic Load Balancer and the Application Load Balancer?

The Classic Load Balancer is the right option for simple load balancing of traffic across several EC2 instances.

On the contrary, the Application Load Balancer is suitable for container-based or microservices architecture where there is either a requirement for routing traffic to different services or carrying out load balancing across multiple ports on the same EC2 instance.
### 47. Can you explain how AWS Elastic Beanstalk applies updates?

Before updating the original instance, AWS Elastic Beanstalk readies a duplicate copy of the instance. Thereafter, it routes the traffic to the duplicate instance so as to avoid a scenario where the update application fails.

In case there is a failure in the update process, the AWS Elastic Beanstalk will switch back to the original instance using the very same duplicate copy it created before beginning the update process.
### 48. What happens if an application stops responding to requests in AWS Elastic Beanstalk?

Even though the underlying infrastructure appears healthy, Beanstalk is able to detect if the application isn’t responding on the custom link. It then logs the situation as an environmental event, which can then be checked in detail and thus, acted upon.

AWS Elastic Beanstalk apps have a built-in system for avoiding underlying infrastructure failures. The Beanstalk uses the Auto Scaling feature to automatically launch a new instance in case an Amazon EC2 instance fails.
### 49. How is the AWS CloudFormation different from AWS OpsWorks?

Although both AWS CloudFormation and AWS OpsWorks provide support for application modeling, deployment, configuration, and management activities, the two differ in terms of the abstraction level and the areas of focus.

AWS CloudFormation is a building block service that allows managing almost any AWS resource via JSON-based domain-specific language. Even without prescribing a distinct model for development and operations, CloudFormation offers foundational capabilities for the AWS.

With AWS CloudFormation, customers can define templates and then use the same to the provision as well as manage AWS application code, resources, and operating systems.

AWS OpsWorks, on the other hand, is a high-level service focusing on providing a highly reliable and productive DevOps experience for IT admins and ops-oriented developers. OpsWorks features a configuration management model and offers integrated experiences for activities like auto-scaling, automation, deployment, and monitoring.

Compared to CloudFormation, OpsWorks provides support for a smaller number of application-oriented AWS resource types, including Amazon CloudWatch metrics, EBS volumes, EC2 instances, and Elastic IPs.
### 50. What happens when one of the resources in a stack can’t be created successfully in AWS OpsWorks?

The automatic rollback on error feature is enabled when one of the resources in a stack can’t be created successfully in AWS OpsWorks. The feature results in the deletion of all the successfully created AWS resources until the point of the occurrence of the error.

Doing so ensures that no error-causing data is left behind as well as abiding by the principle that the stacks are either created completely or not created at all.

The automatic rollback on error feature is useful especially in cases where one might unknowingly exceed the limit of the total number of Elastic IP addresses or does not have access to the EC2 AMI.
Focus on These AWS Interview Questions

That sums up the list of top AWS technical interview questions list. These should give you a solid grounding in AWS, though you should read more. We have a collection of the AWS tutorials to help you learn even more about the cloud computing service.

The AWS interview questions and answers is by no means an exhaustive list. That’s why you should do a lot more googling and reading so that you can ace that interview.  The interview questions on AWS could be anything, as it is quite a broad topic, so make sure you have as wide an understanding of the subject as possible.

### 51.What is EC2?
Amazon EC2 or Elastic Compute Cloud enables businesses to run their applications on the cloud. It is a Virtual Machine hosted in the cloud to which the business has an operating system-like control. It is a cloud-based server similar to an on-premises server, with all-time control so that you can access it at any time and from anywhere.

### 52.Tell us about Snowball?
Snowball is a solution for data transfer that helps in the secure transfer of petabytes of data into and out of the AWS cloud. With the help of Snowball, the data can be transferred with security, at affordable cost, and in less time.

### 53.What is cloudwatch in AWS?
Cloudwatch is a monitoring service that helps to keep track of AWS services, hybrid services, and on-premises applications. It helps in collecting performance and operational data and provides actionable insights with which businesses can optimize operations and understand operational health. It keeps an eye on the complete stack and triggers alarms to automate actions and reduce the time for resolution. Thus, important business time is freed up and business can focus on growth.

### 54.Name three basic cloud services. Mention AWS products built using them.
The three basic cloud services are Computing, Networking, and Storage. Below are the AWS products built using these services:

* Computing: AWS products such as EC2, Lightstat, Lambda, Elastic Beanstalk, and Auto-scaling are built using the computing services.
* Networking: AWS products such as Amazon CloudFront, VPC, and Route 53 use Networking services.
* Storage: AWS products such as Elastic File System, Elastic Block Storage, S3, and Glacier use Storage services.

### 54.Tell us about AWS Lambda.
AWS Lambda is a compute service that is event-driven and does not require a server. It can run codes for almost all types of applications without managing servers. It is available for more than 200 AWS services and SaaS applications in a pay-per-use model.

**Read more about Lamda function:**
[AWS Lambda Functions Qustions & Answers](https://haithai91.medium.com/aws-lambda-essentials-interview-questions-88b2c61341a3)


# AWS Lambda 

### 1. What is AWS Lambda?

It is an AWS serverless computing service offered by Amazon Web Services that runs the code in response to events and automatically manages the compute resource.

[Source >>](https://intellipaat.com/)

### 2. What are the languages supported by AWS Lambda?

The languages supported by AWS Lambda are as follows:

    Java
    Python
    js
    C#
    Ruby
    Go
    PowerShell

[Source >>](https://intellipaat.com/)

### 3. What is automated deployment?

While automated deployment is similar to programming in other languages, it cuts down a lot of associated challenges. It also cuts down all human interferences; this, in turn, helps organizations ensure quality-based outcomes that are best in every parameter. As one becomes more proficient in it, deployment of the pipeline can easily be created.

[Source >>](https://intellipaat.com/)

## 4. What is Auto Scaling in Lambda?

It is one of the features of AWS that helps one to automatically configure and spin novel instances. One of the best things about AWS Auto Scaling is that it does not require any interference at any stage. However, users can monitor everything through metrics and thresholds. To enable this task, one needs to cross a threshold, and without interference, one can see the instances scaled horizontally.

[Source >>](https://intellipaat.com/)

### 5. What type of storage is provided by Amazon?

There are different types of storage options provided by Amazon that are effective in terms of durability as well as performance. While the combination of storage access works fine, independent access can also be provided as per the requirements.

The first storage is EBS, which is actually block-level storage. It has an encryption feature and is a good option to consider when independent storage is required.

The next storage type is EC2 instance, which is a good fit for permanent storage needs. It is directly connected to the host PC as a storage disk. The data on this storage is valid as long as the instance is valid.

Another type of Amazon storage is called the Adding storage, which contains all information related to the boot instance. Amazon S3 is another option available for storage that can store large amounts of data and is often known to be an inexpensive storage option.

[Source >>](https://intellipaat.com/)

### 6. While performing DDOS, what is the limit for execution in Lambda?

The limit is five minutes while performing DDOS.

[Source >>](https://intellipaat.com/)

### 7. What do you think makes Lambda a timesaving approach?

There can be a number of reasons behind this. One of which is that Lambda stores everything in a local server memory.  Another reason can be that data is stored directly in the database without it affecting the performance. In addition to these features, Lambda also has simple testing techniques; for example, integration testing can be made powerful through multiple vendors.

Before moving ahead, you can check out this AWS Lambda YouTube tutorial to gain a better understanding of the topic.

[Source >>](https://intellipaat.com/)

### 8. What is your understanding of AMI?

AMI is Amazon Machine Image; it provides the information required to launch an instance. One can also launch multiple instances using AMI when there are multiple vendors.

[Source >>](https://intellipaat.com/)

### 9. Do you think there is a relation between Instance and AMI?

Yes, they are related to each other. An instance is a virtual machine with particular specifications and OS that one can choose while creating them. While AMI or Amazon Machine Image is the complete backup of an instance.

[Source >>](https://intellipaat.com/)

### 10. What are the best practices for security in Lambda?

Using AWS IAM (Identity Access and Management) is one of the widely used security practices in Lambda. Granting specific user access to particular roles is another effective option to enhance security. In this security practice, access can be restricted to hosts that are not trusted or authorized. In addition to this, no matter how effective and stringent the security protocols are, they should always be updated timely.

[Source >>](https://intellipaat.com/)

### 11. What is elastic blockage storage in Lambda?

Amazon’s elastic block storage (EBS) can be defined as a virtual storage area network where tasks can be started. It can tolerate faults easily, and users need not worry about loss of data even if the disk is damaged in the RAID. Provisioning and allocating the storage can also be done in EBS. If required, it can also be connected to an API.

[Source >>](https://intellipaat.com/)

### 12. How does Lambda handle failure during event processing?

In Lambda, a function is run in either synchronous or asynchronous mode. If a function fails in synchronous mode, then it just gives an exception to the calling application. If a function fails in asynchronous mode, then it is retried at least three times.

[Source >>](https://intellipaat.com/)

### 13. Is vertical scaling possible in Lambda?

Yes, vertical scaling is possible in Lambda. Vertical scaling is one of the  most in-demand features of AWS Lambda. This feature is generally used when a user needs to spin a larger instance. If, in case, they are already using an instance, it can be paused and detached from the server. In this process, it is important to note the ID of the new device post that can continue the process.

[Source >>](https://intellipaat.com/)

### 14. What are the limitations of AWS Lambda?

 Some of the limitations of AWS Lambda are as follows:

    The default deployment package size is 50 MB.
    The ephemeral disk space is limited to 512 MB as the Lambda function will take longer time to execute with a larger package size.
    The execution time is more when the memory allocation is less.
    The memory range is from 128 MB to 10,240 MB.
    The maximum execution timeout for a function is 15 minutes.
    
  [Source >>](https://intellipaat.com/)

### 15. How is a Lambda function executed?

A Lambda function can be directly invoked by the Lambda console, Lambda API, AWS SDK, AWS CLI, and AWS toolkits.

[Source >>](https://intellipaat.com/)

### 16. Name a simple method to improve performance in AWS Lambda.

Performance in AWS Lambda can be simply improved by using RAID, the Linux software. It also helps in increasing security.

[Source >>](https://intellipaat.com/)

### 17. In how many ways can AWS Lambda be used?

One can use Lambda in the following ways:

    As an event-driven compute service, AWS Lambda runs code in response to events.
    These events can be the changes to data in an Amazon S3 bucket or AWS DynamoDB
    Lambda can run code in response to HTTP requests using Amazon API Gateway or API calls made using AWS SDKs.
    
 [Source >>](https://intellipaat.com/)
 
 
### 18. How does AWS Lambda secure my code?

Lambda secures the code by encrypting it. Lambda stores the code in Amazon S3 buckets and encrypts it when it is resting. Further, AWS Lambda performs an additional integrity check on the code while it is running.

 [Source >>](https://intellipaat.com/)

### 19. What is serverless computing?

Serverless computing is a cutting-edge computing execution model wherein a cloud provider runs the virtual server and dynamically manages the allocation of machine resources. Serverless computing helps build and run applications and services without being concerned about servers. With the prowess of serverless computing, applications run on servers, but the servers are managed by AWS. This gives developers a lot of flexibility and freedom to focus on app development. AWS Lambda is at the core of serverless computing as it helps to run code without servers.

 [Source >>](https://intellipaat.com/)

### 20. What is the procedure to build an AMI ?

To build an AMI, first you need to get an instance from another trusted AMI. After this, you need  to add components, as well as packages. You can avoid adding data if it is sensitive due to security reasons. As the next step, add the access credentials post which you can sign up with a database. The total amount of data that you need and stored already can be enhanced up to any level depending on the exact requirements.

 [Source >>](https://intellipaat.com/)

### 21. Do Lambda-based functions stay available after the code or configuration is changed?

Yes, Lambda-based functions remain available after the code or configuration is changed. When a Lambda function is updated, there is a brief period, less than a minute, when requests can be served by either the old or new version of the function.

 [Source >>](https://intellipaat.com/)

### 22. What are the restrictions applied to the AWS Lambda function code?

Although AWS Lambda has very few restrictions on various kinds of operating systems activities and standard programming languages, there are a few restrictions on activities that disable instances and trace calls and inbound network connections. In addition to this, AWS Lambda also disables activities such as debugging systems and TCP ports. For outbound data connection, TCP or IP sockets are very supportive.

 [Source >>](https://intellipaat.com/)


### 23. How to get started with a serverless application?

In order to get started with a serverless application, a user needs to console AWS Lambda and download the blueprint. The original file that will be downloaded should have an AWS Sam file, also known as AWS resource in the application, and a ZIP file. AWS Cloud formation commands can be used for packaging and deploying serverless application codes and documentation can also be performed.

 [Source >>](https://intellipaat.com/)

### 24. What are the disadvantages of using the serverless approach?

Everything in AWS Lambda comes with its own merits and demerits depending on the task performed. The upper limit is strictly on the vendor control in the serverless approach and offers more downtime. Sometimes there is a loss of system functionality and the system’s limits are other issues; no dedicated hardware is available for AWS serverless approach. In most cases, customer errors can also give rise to problems.

 [Source >>](https://intellipaat.com/)

### 25. What is the difference between an anonymous class and the Lambda function?

One of the biggest differences between an anonymous class and the Lambda function is the use of keywords. While the keywords in a Lambda function are used to resolve functional classes, the keywords in anonymous classes are used to resolve anonymous functional classes.

 [Source >>](https://intellipaat.com/)

### 26. Is Lambda Expression a nameless suspension of code?

Yes, it is a nameless suspension of code.

 [Source >>](https://intellipaat.com/)

### 27. What kind of code can run on AWS Lambda?

There are many activities that can be performed on AWS Lambda; for example, it can be used to build mobile backends from Amazon DynamoDB to retrieve and transform data. Handlers transform and compress objects as they get uploaded to Amazon S3. This is done by using Amazon Kinesis, serverless processing of streaming data. The reporting and auditing of API calls can be made to any web service of Amazon, and many other activities can also be done with the help of AWS Lambda.

 [Source >>](https://intellipaat.com/)

### 28. What are final variables and effectively final variables in Lambda?

Final variables are those that cannot be modified once assigned, while effectively final variables can be changed as they are in their earlier stage and have not been assigned a value. Effectively final variables play a huge role in testing as well. If final variables are to be equipped with several additional features, this can be done through effectively final variables.

 [Source >>](https://intellipaat.com/)

### 29. How does AWS Lambda work?

Many people consider AWS Lambda to be a little confusing, but it is not. It is just a simple four-step process that begins with uploading code to AWS Lambda. The next step is to set up your code to trigger from other AWS services, HTTP endpoints, or mobile apps. AWS Lambda will only run a code when it is triggered and will only use the computing resources needed to run it.

 [Source >>](https://intellipaat.com/)

### 30. What can one build with AWS Lambda?

The following is the list of what all can one build with AWS Lambda:

    Real-time file processing
    Sorting real-time stream processing
    Data processing
    Data validation
    Filtering
    Third-party API requests


 [Source >>](https://intellipaat.com/)


