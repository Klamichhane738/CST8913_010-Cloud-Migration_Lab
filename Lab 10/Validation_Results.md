
# Validation Results

## Application Deployment
Post-migration, the “Hello World” application was verified to function properly in the Azure environment which was accessed using the public ip address of migrated VM.
![Alt text](Screenshots/Milestone6%20Validation%20and%20Failover/1.%20Accessing%20webpage%20using%20VM%20public%20ip.png )

#### Functionality Test
The web application was accessible without errors, and basic interactions performed as expected.

## Failover Test
To test the failover, the migrated VM was restarted after changing its password to check if the website was running smoothly and it worked.

A failover scenario was tested to ensure the VM's resilience, confirming minimal downtime and quick recovery.
![Alt text](Screenshots/Milestone6%20Validation%20and%20Failover/4.%20Failover%20details.png )

## Accessing VM using RDP
After assigning public ip to the migrated VM, Azure was able to connect to Windows server and access it easily.
![Alt text](Screenshots/Milestone5%20VM%20migration%20execution/36.%20Accessing%20VM%20through%20RDP.png)

### Outcome
- **Uptime**: 99.9% as per Azure's SLAs.
- **Failover Success**: Test completed successfully with automatic failover mechanisms in place.
