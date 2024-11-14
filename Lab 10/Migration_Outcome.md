
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

**Solution Implemented**:  
To address this issue, a static IP address was manually assigned to the network settings:

1. **Accessed Network Settings**:
   - Navigated to the **Network and Sharing Center** on the VM.
   - Opened **Network Adapter Properties**.

2. **Configured Static IP Address**:
   - Selected **Internet Protocol Version 4 (TCP/IPv4)** and set a static IP address that aligned with the existing network configuration.
### 3. Issue with Microsoft Azure Site Recovery Unified Agent

**Problem**:  
The default Microsoft Azure Site Recovery Unified Agent had issues configuring the configuration server details.

**Solution**:  
Manually searched for and installed an older version, **Microsoft ASR 9.24.1.0**, which successfully allowed configuration of the server details.
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

### 6. RDP Connection Issue After VM Migration

**Problem**:  
After the VM was fully migrated, RDP failed to connect to the VM despite the RDP port being correctly assigned in the NSG settings.

**Solution**:  
Changed the VM's password and restarted the VM, which resolved the issue and allowed successful RDP connection.

## Lessons Learned
- Pre-assessment of network configurations can prevent connectivity issues.
- Storage compatibility checks should be part of initial evaluations.
