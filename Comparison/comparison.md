# Cloud Resource Comparison Across AWS, Azure, and Google Cloud

**Objective:**  
The main objective is to understand Cloud resources through research and identify equivalent cloud services across AWS, Microsoft Azure, and Google Cloud based on descriptions of 30 common cloud resources.

| #  | Description                                                                                   | AWS (Service Name)      | Azure (Service Name)        | Google Cloud (Service Name) |
|----|-----------------------------------------------------------------------------------------------|-------------------------|-----------------------------|-----------------------------|
| 1  | A compute service that provides scalable virtual machines for running applications.            | EC2                     | Virtual Machines            | Compute Engine              |
| 2  | An object storage service used to store and retrieve data, commonly used for backups and static website content. | S3                      | Blob Storage                | Cloud Storage               |
| 3  | A managed relational database service that supports multiple database engines like MySQL, PostgreSQL, and SQL Server. | RDS                     | Azure SQL Database          | Cloud SQL                   |
| 4  | A serverless compute service that allows you to run code in response to events without provisioning or managing servers. | Lambda                  | Azure Functions             | Cloud Functions             |
| 5  | A virtual private network service that allows you to create isolated networks within the cloud provider's infrastructure. | VPC                     | Virtual Network             | Virtual Private Cloud (VPC) |
| 6  | A content delivery network (CDN) service that delivers data, videos, applications, and APIs to customers around the world with low latency. | CloudFront              | Azure CDN                   | Cloud CDN                   |
| 7  | A managed NoSQL database service designed for low-latency, high-scale applications.             | DynamoDB                | Azure Cosmos DB             | Firestore                   |
| 8  | A block storage service for use with virtual machines, offering persistent storage for data.    | EBS                     | Azure Managed Disks         | Persistent Disk             |
| 9  | A managed container orchestration service based on Kubernetes.                                 | EKS                     | Azure Kubernetes Service (AKS) | Google Kubernetes Engine (GKE) |
| 10 | A service for managing user access and encryption keys to secure cloud resources.               | IAM + KMS               | Azure Active Directory + Key Vault | IAM + Cloud Key Management  |
| 11 | A platform that automates application deployment and scaling without needing to manage infrastructure. | Elastic Beanstalk       | App Service                 | App Engine                  |
| 12 | A service that provides monitoring and logging of applications and infrastructure, offering insights into resource usage and performance. | CloudWatch              | Azure Monitor               | Cloud Monitoring + Logging  |
| 13 | A domain name system (DNS) service that routes traffic globally and translates domain names to IP addresses. | Route 53                | Azure DNS                   | Cloud DNS                   |
| 14 | A load balancing service that distributes incoming network traffic across multiple targets, improving application availability. | Elastic Load Balancing (ELB) | Azure Load Balancer         | Cloud Load Balancing        |
| 15 | A service that automatically scales your cloud infrastructure based on demand, ensuring resources are available as needed. | Auto Scaling            | Azure Autoscale             | Autoscaler                  |
| 16 | A message queuing service that enables applications to send and receive messages between different components. | SQS                     | Azure Queue Storage         | Pub/Sub                     |
| 17 | A managed real-time data streaming service that collects and processes large amounts of data from various sources. | Kinesis                 | Azure Event Hubs            | Dataflow                    |
| 18 | A fully managed, highly scalable data warehouse service optimized for analytics and large-scale queries. | Redshift                | Azure Synapse Analytics     | BigQuery                    |
| 19 | A service that automates the execution of workflows and allows the integration of different cloud services in a sequence of steps. | Step Functions          | Logic Apps                  | Cloud Workflows             |
| 20 | A service that integrates multiple data sources and enables data migration, transformation, and movement across platforms. | Data Pipeline           | Data Factory               | Dataflow                    |
| 21 | A data catalog and governance service that helps manage metadata across your data estate, supporting compliance and security. | Glue                    | Azure Purview               | Data Catalog                |
| 22 | A set of machine learning and AI services that provide pre-built models, APIs, and tools for developers to easily implement AI in their apps. | SageMaker               | Azure Machine Learning      | AI Platform (Vertex AI)     |
| 23 | A service that allows you to define and deploy infrastructure using code, automating the management of cloud resources. | CloudFormation          | Azure Resource Manager (ARM) | Deployment Manager          |
| 24 | A fully managed CI/CD service that automates the building, testing, and deployment of applications to production environments. | CodePipeline            | Azure DevOps Pipelines      | Cloud Build                 |
| 25 | A desktop as a service (DaaS) offering that allows you to deploy virtual desktops in the cloud and access them remotely. | WorkSpaces              | Azure Virtual Desktop       | Cloud Workstations          |
| 26 | A backup and disaster recovery service that helps to protect your data by creating backups and replicas of your cloud resources. | AWS Backup              | Azure Backup                | Backup and DR (Disaster Recovery) |
| 27 | A service designed for big data analytics, allowing organizations to store, process, and analyze large datasets in real time. | EMR                     | HDInsight                  | Dataflow / Dataproc         |
| 28 | A file storage service for storing and sharing files with users, typically used in shared file systems across applications. | EFS                     | Azure Files                 | Filestore                   |
| 29 | A service that helps you transcode, process, and stream media content such as video and audio.  | Elastic Transcoder      | Azure Media Services        | Transcoder                  |
| 30 | A real-time communication service used for sending notifications, emails, and text messages to users and devices. | SNS                     | Azure Notification Hubs     | Firebase Cloud Messaging (FCM) |

## Report

Computing resources such as virtual machines and serverless computing alternatives are provided by AWS, Azure, and GCP in a comparable manner. Every cloud provider provides unique features and services to meet various needs. Businesses can choose the platform that best suits their unique needs and preferences thanks to this. The comparison of these service providers holds some similarities and differences with their counterparts (Comparing AWS, Azure, GCP | DigitalOcean, 2024).

When AWS and Azure are compared, they are found to have more than 200 services available to users. With more than 250 services, AWS offers the largest inventory. Azure is a close second with over 200 services, excelling in analytics, AI, and machine learning. With roughly the same number of services as Azure, GCP is rapidly catching up with its counterparts (Wickramasinghe, 2021). Even if they provide identical services in a variety of disciplines, there are parallels as well as distinctive qualities in the way they organize, label, and distinguish their products.

### Key similarities:

1. **Compute Services**: Virtual machines from all three providers are capable of scaling and can be set up to accommodate a range of multiple use cases. Google Cloud offers Compute Engine, Azure offers Virtual Machines, while AWS offers Elastic Compute Cloud (EC2). Because of their flexibility, users can choose the instance type, region, and storage according to their workloads with these services.
2. **Object Storage**: Similar features like lifecycle management, versioning, and cross-region replication are provided by AWS S3, Azure Blob Storage, and Google Cloud Storage in addition to scalable object storage.
3. **Serverless Computing**: These services, which let customers run programs without worrying about infrastructure administration, are provided by all of the providers.
4. **Managed Kubernetes**: Known as the industry standard for container orchestration, Kubernetes is offered by AWS EKS, Azure Kubernetes Service (AKS), and Google Kubernetes Engine (GKE).
5. **Database Services**: All providers support NoSQL and managed relational databases. Managed MySQL, PostgreSQL, and SQL Server instances are offered by AWS Relational Database Service (RDS), Azure SQL Database, and Google Cloud SQL.

### Differences and Unique Features:

1. **Hybrid Cloud Architecture**: Azure sets itself apart with its robust integration with on-premises infrastructure, made possible by services like Azure Stack and Azure Arc, which support hybrid cloud environments. Azure also boasts a global reach. One of the main ways that Azure differs from AWS and Google Cloud is that it focuses on enterprise-level services, integrates with Microsoft products, and offers hybrid cloud solutions.
2. **Best for Data Analytics**: Google Cloud is the best option for AI/ML and data analytics because it places a great focus on scalable solutions and cutting-edge technologies.
3. **Automation and Orchestration**: With products like AWS CloudFormation and Step Functions, AWS is a leader in offering automation and orchestration services. AWS has an orchestration advantage through CloudFormation's extensive interaction with AWS services, which enables customers to build and manage complex infrastructure deployments through infrastructure-as-code (IaC).
4. **Data Warehousing**: BigQuery from Google Cloud is remarkable for its outstanding scalability and serverless architecture among other cloud providers. It is a special service provided by Google Cloud Platform (GCP) that makes it simple and rapid for customers to examine massive amounts of data. Users don't need to worry about setting up or managing servers using BigQuery because it is fully managed and serverless, unlike AWS's Amazon Redshift and Azure's Synapse Analytics.
5. **Pricing Model Services**: The cost structures and cost management solutions offered by AWS, Azure, and Google Cloud are different. Different user categories can choose from a range of pricing models offered by AWS, including spot instances, reserved instances, and pay-as-you-go. Though their concepts are similar, Azure and Google Cloud are distinguished by their dedicated usage contracts, cost control features, and discounts.
6. **Smooth Integration with Microsoft Products**: Microsoft Azure operates without any problem with Microsoft programs (Office 365, Dynamics, etc.).

### Naming Conventions

Regarding naming conventions for comparable services, each cloud provider has its method.

- **AWS**: AWS descriptively labels its services, frequently highlighting the essential features (e.g., RDS for relational databases, S3 for storage, and EC2 for computation).
- **Azure**: Microsoft's larger ecosystem and enterprise focus are strongly linked to Azure's naming rules. Their functionality is immediately reflected in services like Azure Virtual Machines and Azure SQL Database, but they also frequently include the "Azure" prefix to create consistent branding.
- **Google Cloud**: The platform's developer-centric and data-oriented focus is frequently emphasized via Google Cloud's nomenclature. BigQuery, Cloud Storage, and Compute Engine, for instance, all concentrate on the main purpose of the service.

### References:

*Comparing AWS, Azure, GCP | DigitalOcean. (2024).* Digitalocean.com.https://www.digitalocean.com/resources/articles/comparing-aws-azure-gcp 

Wickramasinghe, S. (2021, October 1). AWS vs Azure vs GCP: *Complete Guide to Cloud Platforms for the Enterprise.* BMC Blogs. https://www.bmc.com/blogs/aws-vs-azure-vs-google-cloud-platforms/

rolyon. (2024). *Azure documentation.* Learn.microsoft.com. https://learn.microsoft.com/en-us/azure/?product=popular

Amazon. (2019). *AWS Documentation.* Amazon.com. https://docs.aws.amazon.com/

*Documentation.* (n.d.). Google Cloud. https://cloud.google.com/docs

‌

‌

‌