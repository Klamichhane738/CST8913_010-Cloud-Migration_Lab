**Note** : All other associated screenshots have been uploaded to Screenshots folder for respective milestones.
# Validation Results

Migrated VM in azure portal :

![alt text](<Screenshots/Milestone5 VM migration execution/29. Resouce group containing migrated VM.png>)

The overview page of migrated vm after assigning public ip address and other virtual network, RDP and NSG configuration.
![alt text](<Screenshots/Milestone5 VM migration execution/29. Migrated Vm overview page.png>)

## 1. Application Deployment
Post-migration, the “Hello World” application was verified to function properly in the Azure environment which was accessed using the public ip address of migrated VM.
![Alt text](Screenshots/Milestone6%20Validation%20and%20Failover/1.%20Accessing%20webpage%20using%20VM%20public%20ip.png )

#### Functionality Test
The web application was accessible without errors, and basic interactions performed as expected.

## 2. Failover Test
To test the failover, the migrated VM was restarted after changing its password to check if the website was running smoothly and it worked.

A failover scenario was tested to ensure the VM's resilience, confirming minimal downtime and quick recovery.
![Alt text](Screenshots/Milestone6%20Validation%20and%20Failover/4.%20Failover%20details.png )

## 3. Accessing VM using RDP
After assigning public ip to the migrated VM, Azure was able to connect to Windows server and access it easily.
![Alt text](Screenshots/Milestone5%20VM%20migration%20execution/36.%20Accessing%20VM%20through%20RDP.png)

# Post migration best practices

**1. Azure Backup** is a reliable service for maintaining backup copies of migrated virtual machines and other data, which can be restored in case of any disaster. Implementing this also aligns with a robust disaster recovery strategy, providing with peace of mind and reducing downtime risks.
![alt text](<Screenshots/Milestone6 Validation and Failover/6. Configuring Azure Backup.png>)

**2. Using Azure Backup Vault** is an excellent post-migration best practice for securing your workloads and data in the cloud. It helps protect against data loss due to accidental deletion, corruption, or disaster events.
![alt text](<Screenshots/Milestone6 Validation and Failover/9. Accessing backup vault.png>)

