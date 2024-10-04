## A solution diagram showing the target architecture with Kubernetes pods and a managed database.

Based on the scenario described in lab instruction, the application consists of two virtual machines. One is WebServerVM and other is SQLVM. As per the requirement of the lab, the web server will be moved to a Managed SQL Database service and containerized using Docker for cloud high availability. Likewsise, it will also be hosted on Azure Kubernetes Service (AKS). A six-hour outage is the most that the application can withstand as mentioned in the instruction.

 Architecture is assumed to have: 

- WebServerVM having a lightweight Node.js application.

- SQLVM hosting a SQL Server database.

<img src="https://github.com/user-attachments/assets/ac520979-ca4f-4a3d-9662-8d0dc810027f" alt="Final" width="800" />

WebServerVM: Containerized Node.js application.

Docker Container: Shows the containerized web application.

AKS Pods: Contains multiple pods running the Node.js application for high availability.

SQLVM: Original SQL Server database before migrating to Azure managed database.

Azure Load Balancer: Responsible for distributing traffic to the AKS pods.

Managed SQL Database: Azure’s managed SQL service for the database.

Azure Virtual Network: Capable of enuring secure communication between components.

### Description of Target Architecture
***Web Server Containerization and Hosting on AKS:*** The WebServerVM is currently hosting a lightweight Node.js application and it will be containerized using Docker. After that, Azure Kubernetes Service (AKS) will be used to deploy this containerized application. The load will be distributed and redundancy provided by many AKS pods.

***Database Migration to Managed SQL Service***
Azure's Managed SQL Database service once migrated will replace the current SQLVM, which now houses a SQL Server database. And due to the integrated high availability, automated backups, and scalability features of this managed service, there is less administrative downtime.

***AKS Cluster***
Multiple clones of the Node.js application will be deployed across various nodes which makes sure of AKS cluster for high availability. This configuration guarantees that the application will continue to function even in the event of a node failure and any other unseen circumstances.

### Container orchestration for scalability and high availability.
This architecture uses Docker to containerize a Node.js application running on a virtual machine (WebServerVM), making deployment and management easier. Next, the container is launched using Azure Kubernetes Service (AKS), which orchestrates, scales, and deploys the containers automatically. AKS has a feature called horizontal pod autoscaling, which lets it handle different traffic volumes effectively by automatically altering the number of pods dependent on the application's load. In order to provide optimal performance and a seamless user experience, it also connects with Azure Load Balancer to distribute incoming traffic evenly among the pods.

Replica sets are used by Azure Kubernetes Service (AKS) to maintain a constant number of identical containers, or pods, operating continuously. The replica set quickly generates a new pod to take the place of any failed pod, so the application continues to function as intended even in the event of a pod failure. For further dependability, AKS can also be configured to distribute these pods over several availability zones within a region. Furthermore, Kubernetes automatically shuts down unhealthy pods and replaces them with new ones in order to maintain system stability. This is done on a regular basis.All of these capabilities ensure *high availability.*

### Migration Procedures

