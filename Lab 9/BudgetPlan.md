# Three-Year Growth and Budget Plan

## Year 1: Migration and Initial Operations

### Overview
The first year involves migrating on-premises infrastructure to GCP, setting up essential services, and establishing initial operational capabilities. Given the one-time migration costs and operational setup, Year 1 has a higher budget allocation to cover these transitional expenses.

### i. Migration Costs
- **Data Transfer**: Migrating 30 TB of data using the Storage Transfer Service is estimated at **$384**, an efficient bulk migration tool to minimize manual transfer costs.
- **Database Replication**: Temporary Cloud SQL and Bigtable instances will be used for database replication. Setting up a primary SQL database costs approximately **$768** for 5 TB, and NoSQL Bigtable replication costs around **$1,740.80** for 10 TB during migration.
- **Compute Resources**: Using 5 Compute Engine instances (n1-standard-4) for temporary migration support, costing **$693.50** monthly during migration.

**Total Migration Cost**: **$3,719.72** (one-time).

### ii. Operational Cost Optimization
- **Reserved Instances for Predictable Workloads**: ShopPro should adopt a mix of 1-year and 3-year reserved instances for essential VMs. Selecting reserved instances for primary VM clusters, such as using 7 VMs (n2-standard v4) in South Carolina with a 3-year discount, costs **$577.99** monthly.
- **Load Balancer Configuration**: Deploy regional load balancers instead of global ones to reduce costs and align with regional traffic needs.

### iii. Management and Monitoring Cost
- **Redundant Storage Setup**: Multi-regional storage for disaster recovery helps avoid higher cross-continent data transfer costs, with an estimated monthly cost of **$471.04**.
- **Cloud Monitoring**: Track only essential metrics and limit log retention to two months, estimated monthly cost for moderate usage monitoring is **$219.95**.

### Total Projected Cost for Year 1
- **Migration**: $3,719.72 (one-time)
- **Annual Operational Costs**: $13863.42 * 12 = **$166,361.04**
- **Annual Management Costs**: $690.99 * 12 = **$8,291.88**
- **Total for Year 1**: **$178,372.64**

---

## Year 2: Cost Optimization and Enhanced Services

With infrastructure established, Year 2 emphasizes cost savings by transitioning to 3-year reserved instances and maintaining efficient configurations.

### i. Operational Scaling and Reserved Instances
- **Reserved Instances**: Transitioning more services to 3-year reserved instances reduces costs, with a new monthly operational cost estimate of **$13,500** (assuming a 7% savings).

### ii. Enhanced Monitoring and Logging
- **Log Retention**: Extended log retention increases management costs slightly, but selective monitoring and targeted logging keep costs reasonable.

### Total Projected Cost for Year 2
- **Annual Operational Costs**: $12,800 * 12 = **$153,000**
- **Annual Management Costs**: Approx. **$9,000**
- **Total for Year 2**: **$162,000**

---

## Year 3: Continued Expansion and Sustainable Management

In Year 3, ShopPro scales infrastructure to handle increased demand, enhancing redundancy and continuing cost-saving practices.

### i. Infrastructure Growth
- **Scaling Cloud Spanner and Storage**: Expanding to meet growing workloads increases operational expenses. New monthly operational cost estimate: **$15,000**.
- **Annual Operational Cost**: **$170,000**.

### ii. Advanced Monitoring and Cost Control
- **Disaster Recovery**: Maintain efficient disaster recovery with multi-regional storage and focused monitoring strategies.

### Total Cost for Year 3
- **Operational**: **$170,000**
- **Management**: **$10,000**
- **Total for Year 3**: **$180,000**

---

## Summary Budget Plan Over Three Years
| Year   | Migration Cost | Operational Cost | Management Cost | Total Cost     |
|--------|----------------|------------------|------------------|-----------------|
| Year 1 | $3,719.72      | $166,361.04      | $8,291.88        | $178,372.64     |
| Year 2 | -              | $153,000         | $9,000           | $162,000        |
| Year 3 | -              | $170,000         | $10,000          | $180,000        |
| **Total 3-Year Budget** | -              | -                | -                | **$520,372.64** |
