
# Assessment Report

## Summary of Findings
The migration assessment was conducted using Azure Migrate. The findings are as follows:

#### Assessment Phase Summary

Initial Setup and Preparation

- Physical Server Specifications:
RAM: 4 GB
Processor: 4-core
Storage: 80 GB

- Migration Server Specifications:
RAM: 16 GB
Processor: 8-core
Storage: 600 GB

- Software Installation: VMware Workstation 2017 was installed, and the Windows Server ISO file was downloaded and activated.
#### Assessment VM Creation and Configuration
A VM was created on VMware Workstation specifically for running the migration assessment.
Necessary Windows Server features were added to run a simple webpage (index.html) on localhost.

![Alt text](Screenshots/Milestone3%20Application%20Deployment/4.%20Running%20localhost.png )
#### Assessment Execution with Azure Migrate
Assessment Process:
The assessment phase was conducted using Azure Migrate, analyzing the readiness of the current infrastructure for migration to Azure.

Phases: 

1. Running Azure Migrate Installer: Running Azure Migrate installer in powershell to run Application Configuration Manager.
![alt text](<Screenshots/Milestone4  Migration Assessment/1. Running azure migrate installer.png>)

2. Next step is configuring Application Configuration manager with ip address and username and password of Vm to be migrated. We also assign project key and link with student azure account to begin the discovery process:
![alt text](<Screenshots/Milestone4  Migration Assessment/2. Verying project key and azure account.png>)
![alt text](<Screenshots/Milestone4  Migration Assessment/3. Assigning Ip address of VM.png>)
![alt text](<Screenshots/Milestone4  Migration Assessment/4. Initiating the discovery.png>)

3. Creating assessment: Assessment was created as shown below: 
![alt text](<Screenshots/Milestone4  Migration Assessment/6. Creating assesment.png>)

Once the above step was dobe,the assessment report was generated in the Azure portal, which provided detailed insights into compatibility, potential challenges, and system requirements.
![alt text](<Screenshots/Milestone4  Migration Assessment/8. Assessment overview.png>)


#### Findings and Outcome
The assessment confirmed that the infrastructure was suitable for migration, identifying essential requirements and ensuring preparedness.

Once assessment was generated, we need to analyze dependencies and install it in the host server.
![alt text](<Screenshots/Milestone4  Migration Assessment/10 Dependencies analysis.png>)

A detailed assessment report was generated within the Azure portal, providing:
Compatibility insights,
potential challenges to be addressed and
system requirements for a successful migration.

The findings highlighted areas where synchronization would be critical during the next phases and emphasized the specifications required for a successful migration.
#### Readiness:
Ready for migration with all necessary prerequisites met.

*Azure readiness:*
![alt text](<Screenshots/Milestone4  Migration Assessment/9. Azure readiness for migration.png>)

## Recommendations
- Double-check that the discovery phase captures all necessary data accurately. Ensure that data points like VM configuration, dependencies, and current usage statistics are complete.
- Validate the accuracy of IP addresses and authentication credentials to avoid interruptions during the assessment.
- Use the assessment findings to identify potential optimizations such as right-sizing VMs to match Azure's offerings for cost-efficiency and performance improvement.
- Provide training sessions for the technical team on using Azure Migrate tools effectively.

Following these recommendations will facilitate a smoother transition from the assessment phase to the actual migration, ensuring minimal disruptions and optimized use of Azure services.
