
# Cloud Migration Plan: Manchester Metropolitan University Case Study

- **End of Support for VMware On-Premises Infrastructure**: As explained in the case study, the university's current on-premises infrastructure was getting old, and support for important services was about to end.
- **Cost Benefits and Licensing**: The university used its existing Microsoft licenses, making Azure VMware Solution a more affordable choice compared to spending money on upgrading its current infrastructure.
- **Reduction in Physical Datacenter**: The case study points out that one of Manchester data centers is set to be demolished, and the university had to quickly downsize its physical infrastructure. To make it happen, they reduced the number of comms racks from 25 to 7.

## Questions to Raise Regarding Manchester University’s Infrastructure

- What important systems and applications are currently operating on the local infrastructure?
- What are the possible security and compliance requirements for student and staff data in the cloud associated with the company?
- How will the company be able to manage and handle the research-data migration procedures to the Azure system?

## RACI Matrix for Migration Team Members

| Task                  | Rob Collins | IT Staff | Azure Solution Architect | Partner (Advania) | Microsoft Support |
|-----------------------|-------------|----------|--------------------------|-------------------|-------------------|
| Migration Planning     | R           | A        | C                        | C                 | I                 |
| Server Migration       | A           | R        | C                        | C                 | I                 |
| Testing and Validation | A           | R        | C                        | I                 | C                 |

**Key**:  
R = Responsible, A = Accountable, C = Consulted, I = Informed

## Best Migration Strategy: Phased Approach with a Hybrid Cloud Model

- **Lift-and-Shift**: Move most systems to Azure VMware Solution quickly with minimal changes.
- **Rearchitect for Azure-Native**: Gradually switch to cloud-native solutions for refreshed servers, like moving research data to Azure Storage.
- **Hybrid Cloud**: Keep some on-premises systems for local access needs, such as building control systems.

## High-Level Migration Schedule

- **Planning & Assessment (2 months)**: This phase requires us to evaluate the existing infrastructure and determine the priorities for servers.
- **Landing Zone Setup (1 month)**: This schedule phase mentions establishing the Azure landing zone.
- **Pilot Migration (2 months)**: Transfer and test a selection of initial servers.
- **Full Migration (4 months)**: Complete the migration of eighty percent of servers and set up monitoring systems.
- **Datacenter Consolidation (1 month)**: Retire old servers and streamline the rack setup in a proper way.

## Main Decision Criteria for Manchester Metropolitan University

- **Cost Efficiency**: Taking advantage of existing Microsoft licenses and Azure VMware Solution is essential to reduce costs.
- **Minimal Disruption**: Maintaining continuous service without interruptions plays a crucial role.
- **Speed**: Most importantly, quick migration is required because of datacenter closure and support deadlines.
- **Cloud-First Strategy**: It covers prioritizing Azure-native solutions for future infrastructure planning.
