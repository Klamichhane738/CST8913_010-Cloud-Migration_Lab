**Note** : All other associated screenshots have been uploaded to Screenshots folder for respective milestones.
# Migration Outcome

## Issues Encountered
During the migration process, the following issues were noted:

### 1. Migration Assessment Issue: VM Validation Using IP Address and Username

**Issue Encountered**:  
During the assessment phase for migrating the Windows Server 2019 hosted on a physical VM to Azure, the validation process required authentication using the server's IP address, username, and password. The assessment tool could only validate the VM if an administrator password had been set during the VM's initial installation. However, in this case, no password was assigned to the administrator account during installation, causing the validation to fail.

**Solution Implemented**:  
To resolve this issue, the following steps were taken:

1. **Accessed the Windows Server through the Server Manager**:
   - Logged into the VM using existing access methods.
   - Opened **Server Manager** and navigated to the **Local Server** section.

2. **Manually Set an Administrator Password**:
   - Accessed the **Users** section under **Computer Management**.
   - Located the built-in **Administrator** account and set a strong password manually.

3. **Re-attempted Validation**:
   - With the administrator password set, re-ran the validation process using the VM's IP address, username, and the newly assigned password.
   - Successfully completed the validation, allowing the assessment phase to proceed.
### 2. Prerequisites Check Warning: Static IP Address in Microsoft Azure Site Recovery Unified Setup

**Issue Encountered**:  
During the prerequisites check phase of the Microsoft Azure Site Recovery (ASR) Unified Setup, a warning was triggered indicating that the VM's network configuration did not have a static IP address assigned. This warning could have impacted the migration and failover process.
![alt text](<Screenshots/Others/Static ip address issue.png>)

**Solution Implemented**:  
To address this issue, a static IP address was manually assigned to the network settings:

1. **Accessed Network Settings**:
   - Navigated to the **Network and Sharing Center** on the VM.
   - Opened **Network Adapter Properties**.

2. **Configured Static IP Address**:
   - Selected **Internet Protocol Version 4 (TCP/IPv4)** and set a static IP address that aligned with the existing network configuration.

![alt text](<Screenshots/Others/Fixing static ip address.png>)
### 3. Issue with Microsoft Azure Site Recovery Unified Agent

**Problem**:  
The default Microsoft Azure Site Recovery Unified Agent had issues configuring the configuration server details.

**Solution**:  
Manually searched for and installed an older version, **Microsoft ASR 9.24.1.0**, which successfully allowed configuration of the server details.

![alt text](<Screenshots/Others/Microsoft ASR.png>)
### 4. Replication Process Detection Issue

**Problem**:  
After the first assessment, the VM was discovered but not detected during the replication intent specification.

**Solution**:  
Performed a second assessment, and after a long waiting period, the VM was finally reflected and detected.
### 5. Replication and Synchronization Issues

**Problem**:  
Replication started but proceeded very slowly. Additionally, an error about an outdated agent version was encountered, causing the replicated VM health status to shift to critical.

**Solution**:  
Updated the agent version on the VM, which resolved the error and restored the ongoing replicated VM's health status to healthy.

![alt text](<Screenshots/Milestone5 VM migration execution/23. Replication status.png>)

### 6. RDP Connection Issue After VM Migration

**Problem**:  
After the VM was fully migrated, RDP failed to connect to the VM despite the RDP port being correctly assigned in the NSG settings.

**Solution**:  
Changed the VM's password and restarted the VM, which resolved the issue and allowed successful RDP connection.

![alt text](<Screenshots/Issues/RDP connection issue.png>)
### Lessons Learned During the Migration Process

1. **Administrator Password Configuration**:  
   Always ensure that an administrator password is set during the initial VM installation. This avoids validation issues during the migration assessment phases.

2. **Static IP Address Setup**:  
   Configure a static IP address on the VM before beginning the migration process. This is crucial to avoid warnings or issues during the prerequisites check.

3. **Agent Version Compatibility**:  
   Always verify that the latest version of the Microsoft Azure Site Recovery Unified Agent is installed. If issues arise, consider rolling back to a stable version (e.g., ASR 9.24.1.0) that is known to work with the configuration server details.

4. **Replication Detection Delays**:  
   Be prepared for delays in the VM detection during the replication process. If the VM is not detected immediately, performing a second assessment may resolve the issue. Patience is key during this phase as it can take longer than expected for the VM to appear.

5. **Replication Speed and Health Issues**:  
   It is essential to monitor replication health and address any errors (such as outdated agent versions) promptly to prevent VM health degradation. Updating the agent often resolves these issues and restores VM health to optimal status.

6. **RDP Connectivity Post-Migration**:  
   After the migration, RDP connection issues can arise, even when the correct ports are configured in NSG settings. Changing the VM's password and restarting the VM can often resolve these connectivity issues.

7. **Snapshot Creation for Recovery**:  
   Creating VM snapshots at critical stages of the migration process is highly recommended. This ensures that if any issue arises, such as configuration errors or replication failures, you can quickly revert to a stable state and resume the process without significant downtime.
