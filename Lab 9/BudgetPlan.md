# Three-Year Growth and Budget Plan

Incorporating specific insights from the cost estimation and optimization strategy documents we have created earlier.

## Year 1: Migration and Initial Operations

### Overview:
The first year involves migrating on-premises infrastructure to GCP, setting up essential services, and establishing initial operational capabilities. Given the one-time migration costs and operational setup, Year 1 has a higher budget allocation to cover these transitional expenses.

### Migration Costs:
- **Data Transfer:** Migrating 30 TB of data using the Storage Transfer Service is estimated at $384, an efficient bulk migration tool to minimize manual transfer costs​ (cost estimation GCP).
- **Database Replication:** Temporary Cloud SQL and Bigtable instances will be used for database replication. Setting up a primary SQL database costs approximately $768 for 5 TB, and the NoSQL Bigtable replication costs around $1,740.80 for 10 TB during migration (cost estimation GCP).
- **Compute Resources:** Using 5 Compute Engine instances (n1-standard-4) for temporary migration support, costing $693.50 monthly during migration (cost estimation GCP).

**Total Migration Cost:** $3,719.72 (one-time).

### Operational Cost Optimization:
- **Reserved Instances for Predictable Workloads:** ShopPro should adopt a mix of 1-year and 3-year reserved instances for essential VMs across regions. For example, using 7 VMs (n2-standard v4) in South Carolina with a 3-year discount costs $577.99 monthly—substantially lower than a 1-year option.
- **Load Balancer Configuration:** Deploy regional load balancers instead of global ones to reduce costs and align with regional traffic needs.

### Management and Monitoring Cost:
- **Redundant Storage Setup:** Multi-regional storage for disaster recovery within the same continent helps avoid higher cross-continent data transfer costs, with an estimated monthly cost of $471.04 (cost estimation GCP).
- **Cloud Monitoring:** Track only essential metrics and limit log retention to two months to keep costs low. Estimated monthly cost for moderate usage monitoring is $219.95 (cost estimation GCP).

**Total Projected Cost for Year 1:** [Calculated based on previous two documents submitted on GitHub]
- **Migration:** $3,719.72 (one-time)
- **Annual Operational Costs:** $14,553.42 * 12 = $174,641.04
- **Annual Management Costs:** $690.99 * 12 = $8,291.88
- **Total for Year 1:** $186,652.64

---

## Year 2: Cost Savings and Efficiency

With infrastructure established, Year 2 emphasizes cost savings by transitioning to 3-year reserved instances, maintaining efficient configurations, and adjusting monitoring needs.

### Operational Scaling and Reserved Instances:
- **Reserved Instances:** Transitioning more services to 3-year reserved instances reduces costs and aligns with predicted growth.
- **New Monthly Operational Cost Estimate:** $13,500 (assuming a 7% savings from 3-year reserved instances).

### Enhanced Monitoring and Logging:
Extended log retention increases the monthly management cost slightly, but selective monitoring and targeted logging keep costs reasonable.

**Total Projected Cost for Year 2:**
- **Annual Operational Costs:** $13,500 * 12 = $162,000
- **Annual Management Costs:** Approx. $9,000
- **Total for Year 2:** $171,000

---

## Year 3: Continued Expansion and Sustainable Management

In Year 3, ShopPro scales infrastructure to handle increased demand. This includes expanding backend services, enhancing redundancy, and continuing cost-saving practices.

### Infrastructure Growth:
- **Scaling Cloud Spanner and Storage:** Expanding to meet growing workloads increases operational expenses.
- **New Monthly Operational Cost Estimate:** $15,000.

**Annual Operational Cost:** $180,000.

### Advanced Monitoring and Cost Control:
Maintain efficient disaster recovery with multi-regional storage and focused monitoring strategies.

**Total Management Cost for Year 3:** $10,000.

**Total Cost for Year 3:**
- **Operational:** $180,000
- **Management:** $10,000
- **Total for Year 3:** $190,000

---

## Summary Budget Plan Over Three Years:

| Year    | Migration Cost | Operational Cost | Management Cost | Total Cost       |
| ------- | -------------- | ---------------- | --------------- | ---------------- |
| Year 1  | $3,719.72      | $174,641.04      | $8,291.88       | $186,652.64      |
| Year 2  | -              | $162,000         | $9,000          | $171,000         |
| Year 3  | -              | $180,000         | $10,000         | $190,000         |
| **Total 3-Year Budget** | - | - | - | **$547,652.64** |
