# Cost Estimation for GCP

## 1. Migration Cost

### 1.1 Data Transfer from On-Premises to GCP
Volume: 30 TB (comprising databases, applications, and other data)  
Transfer Method: Storage Transfer Service  
Cost Calculation: 30,720 GB * $0.0125 per GB = $384

| Volume | Transfer Method               | Cost Calculation                                  |
|--------|--------------------------------|---------------------------------------------------|
| 30 TB  | Storage Transfer Service       | 30,720 GB * $0.0125 per GB = $384                 |

### 1.2 Database Replication Costs
Replicating databases to GCP involves setting up Cloud SQL instances and synchronizing data.

#### Primary SQL Database
Instance Type: db-n1-standard-4  
Storage: 5 TB SSD  
Duration: 1 month (for migration period)  
Cost Calculation: $0.15 per GB per month * 5,120 GB = $768

| Instance Type        | Storage | Duration | Cost Calculation                                   |
|----------------------|---------|----------|----------------------------------------------------|
| db-n1-standard-4     | 5 TB SSD | 1 month  | $0.15 per GB per month * 5,120 GB = $768          |

#### NoSQL Database (Bigtable)
Nodes: 2  
Storage: 10 TB SSD  
Duration: 1 month  
Cost Calculation: $0.17 per GB per month * 10,240 GB = $1,740.80

| Nodes | Storage | Duration | Cost Calculation                                   |
|-------|---------|----------|----------------------------------------------------|
| 2     | 10 TB SSD | 1 month | $0.17 per GB per month * 10,240 GB = $1,740.80    |

### 1.3 Temporary Migration Resources

#### Compute Engine Instances
Type: n1-standard-4  
Quantity: 5 instances  
Duration: 1 month  
Cost Calculation: $0.1900 per hour * 730 hours * 5 instances = $693.50

| Type          | Quantity | Duration | Cost Calculation                                |
|---------------|----------|----------|-------------------------------------------------|
| n1-standard-4 | 5        | 1 month  | $0.1900 per hour * 730 hours * 5 instances = $693.50 |

#### Cloud Storage for Temporary Data
Storage Class: Standard  
Volume: 5 TB  
Duration: 1 month  
Cost Calculation: $0.026 per GB per month * 5,120 GB = $133.12

| Storage Class | Volume | Duration | Cost Calculation                                  |
|---------------|--------|----------|---------------------------------------------------|
| Standard      | 5 TB   | 1 month  | $0.026 per GB per month * 5,120 GB = $133.12     |

### 1.4 Security and Compliance Setup
Cloud Key Management Service (KMS):  
Key Rings: 1  
Keys: 5  
Cost Calculation: $0.06 per active key version per month * 5 keys = $0.30

| Service                       | Quantity | Cost Calculation                               |
|-------------------------------|----------|------------------------------------------------|
| Cloud Key Management Service   | 5 keys   | $0.06 per active key version per month * 5 keys = $0.30 |

**Total Estimated Migration Cost: $3,719.72**

---

## 2. Operational Cost

### 2.1 Web Front-End Cluster
Below is the cost estimation for running VM across different region on various plans:  
A table summarizing the Web Front-End Cluster configuration for 10 instances on GCP Compute Engine with the specified settings:

Region: South Carolina (east-us), Finland (europ-north), and Taiwan (asia-east1)

| Region           | 1-Year Reserved (Ubuntu Pro License) | 3-Year Reserved (Ubuntu Pro License) | Bring Your Own Device (3-Year) |
|------------------|--------------------------------------|--------------------------------------|--------------------------------|
| East US: South Carolina | $1,201.20                         | $796.69                              | $754.73                        |
| North Europe: Finland   | $1,317.93                         | $872.80                              | $830.84                        |
| East Asia: Taiwan       | $1,352.90                         | $892.99                              | $851.03                        |

### 2.2 Load Balancer
An estimated monthly cost breakdown for deploying five standard-tier load balancers in Google Cloud Platform (GCP) across the specified regions, each processing 1,000 GB of data:

| Region               | Scope    | Number of Load Balancers | Data Processed (GB) | Monthly Cost |
|----------------------|----------|--------------------------|----------------------|--------------|
| East US: South Carolina | Regional | 5                        | 1000                 | $19.85       |
| North Europe: Finland | Regional | 5                        | 1000                 | $22.24       |
| East Asia: Taiwan    | Regional | 5                        | 1000                 | $19.85       |

### 2.3 CDN Configuration Cost
The Cloud CDN configuration with the total monthly cost at the end:

| Category               | Region                       | Usage | Unit |
|------------------------|------------------------------|-------|------|
| Cache Data Transfer Out| Asia Pacific (including Hong Kong) | 500 GiB  |
|                        | China                        | 500 GiB  |
|                        | Europe                       | 500 GiB  |
|                        | North America (including Hawaii) | 2 TiB  |
|                        | Oceania                      | 0 GiB   |
|                        | South America                | 500 GiB  |
|                        | All other destinations (including Mexico, Central America, and Middle East) | 0 GiB   |
| Cache Fill            | Within North America or Europe (including Hawaii) | 400 GiB  |
|                        | Within each of Asia Pacific, South America, Middle East, Africa, and Oceania (including Hong Kong) | 400 GiB  |
|                        | Inter-region cache fill (e.g., between Europe and Oceania) | 0 GiB   |

**Total Estimated Monthly Cost: $420.34**

### 2.4 For the API Back-End Services Running Microservices
For the API Back-End Services setup, where ShopPro International uses a microservices architecture with 50 microservices hosted across 20 VMs, here’s a recommended configuration table based on the given information.

We selected the operating system as Ubuntu Pro for all of the regions which is slightly higher than bring your own device strategy.

| Region                | VM Configuration             | Base Quantity | Discounted Option | Monthly Base Cost | Estimated Peak Cost (with 50% Scaling) |
|-----------------------|------------------------------|---------------|-------------------|-------------------|----------------------------------------|
| South Carolina (East US) | General purpose, n2-standard v4 | 7 VMs        | 3-year           | $577.99           | Approx. $1,440.00                      |
| Finland (North Europe) | General purpose, n2-standard v4 | 7 VMs        | 3-year           | $633.19           | Approx. $1,525.00                      |
| Taiwan (East Asia)      | General purpose, n2-standard v4 | 6 VMs        | 3-year           | $556.08           | Approx. $1,470.00                      |

### 2.4.1 Cost of Global Load Balancer for API Backend
Load Balancer scope: Global  
Region: South Carolina  
Number of forwarding rules: 7  
Amount of data processed: 1000 GB  
Total Monthly Cost: $42.45

| Region               | Scope   | Number of Forwarding Rules | Data Processed | Monthly Cost |
|----------------------|---------|----------------------------|----------------|--------------|
| South Carolina       | Global  | 7                          | 1000 GB        | $42.45       |

### 2.5 Payment Processing Section
VM Configuration for PCI Compliance

VM Type: Use D-series or E-series VMs, such as D2s_v4 (2 vCPUs, 8 GB RAM), which are suitable for general-purpose workloads with sufficient security configurations.

| Region                | VM Configuration      | Quantity | Monthly VM Cost (3-Year Discounted) + Bring Your Device |
|-----------------------|-----------------------|----------|--------------------------------------------------------|
| South Carolina (East US) | Compute Optimized, C2-standard-c4 | 5 VMs     | $309.86                                             |
| Finland (North Europe) | Compute Optimized, C2-standard-c4 | 5 VMs     | $341.17                                             |

### 2.6 Estimation Cost for Database Layer

#### 2.6.1 Primary Database (5 TB SQL Database)
The table summarizes the details of the 5 TB Google Cloud SQL (Managed SQL Service) in the South Carolina region for ShopPro International's cloud migration cost estimation:

| Configuration Item         | Details                      |
|----------------------------|------------------------------|
| Service Type               | MySQL                        |
| Region                     | South Carolina (us-east1)    |
| Cloud SQL Edition          | Enterprise                   |
| Number of Instances        | 1                            |
| Total Instance Usage Time  | 730 hours per month          |
| SQL Instance Type          | db-standard-4 (4 vCPUs, 15 GiB RAM) |
| High Availability Configuration | Enabled                |
| Storage Provisioned        | 5 TiB                        |
| Storage Type               | SSD                          |
| Backup Size                | 1 TiB                        |
| Committed Use Discount     | 3 Years                      |
| Total Monthly Cost         | $1,047                       |

#### 2.6.2 Analytics Database (10 TB NoSQL Database - Bigtable)
Bigtable configuration based on a 3-year committed use discount is shown below:

| Configuration Parameter      | Specification                    |
|------------------------------|----------------------------------|
| Region                       | South Carolina (us-east1)        |
| Node Count                   | 2 nodes                          |
| Total Node Usage Time        | 1,460 hours per month            |
| Storage Type                 | SSD                              |
| Storage Amount               | 10 TiB                           |
| Committed Use Discount       | 3 years                          |
| Total Monthly Cost           | $1,613.88                        |

### 2.6.3 BigQuery
BigQuery ML setup for ShopPro International's data processing needs with a logistic regression model.

| Configuration Item         | Details                    |
|----------------------------|----------------------------|
| Service Type               | BigQuery ML                |
| Location Type              | Multi-region               |
| Location                   | United States (multi-region) |
| Model Type                 | Logistic Regression        |
| Amount Processed           | 15 TiB                     |
| Prediction                 | 5 TiB                      |
| Total Monthly Cost         | $4,406.25                  |

### 2.7 Estimation for Data Analytics and ML Processing VM
Compute Engine setup with an Accelerator-Optimized VM (A2) instance and GPU for data processing in GCP.

| Configuration Item         | Details                    |
|----------------------------|----------------------------|
| Number of Instances        | 1                          |
| Total Instance Usage Time  | 730 hours per month        |
| Instances with Public IP   | None (0 ephemeral, 0 static) |
| Operating System / Software| Paid: Ubuntu Pro           |
| Provisioning Model         | Regular                    |
| Machine Family             | Accelerator-optimized      |
| Series                     | A2                         |
| Machine Type               | a2-highgpu-1g (12 vCPUs, 85 GiB RAM, 1 GPU) |
| Threads per Core           | 1 thread per core          |
| Boot Disk Type             | Balanced persistent disk   |
| Boot Disk Size             | 10 GiB                     |
| Region                     | South Carolina (us-east1)  |
| Total Monthly Cost         | $2,729.12                  |

### 2.8 Cloud Composer for Scheduled Batch Jobs
Cloud Composer is set up for scheduled batch jobs for data processing in ShopPro International's configuration.

| Configuration Component   | Specification                   |
|---------------------------|----------------------------------|
| Region                    | South Carolina (us-east1)       |
| Environment Size          | Small                           |
| Average Hours Each Server Runs | 730 hours per month       |
| Airflow Schedulers        | 1 scheduler, 0.5 CPU, 1.875 GiB memory, 1 GiB storage |
| Airflow Workers           | 1 worker, 0.5 CPU, 1.875 GiB memory, 1 GiB storage |
| Airflow Web Server        | 0.5 CPU, 1.875 GiB memory, 1 GiB storage |
| Airflow Triggerers        | 1 triggerer, 0.5 CPU, 1.875 GiB memory, 1 GiB storage |
| Airflow Database          | 1 GiB storage                  |
| Total Monthly Cost        | $349.33                         |

---

## 3. Management Cost

### 3.1 Encryption at Rest (Cloud Key Management) Cost Estimation
Assuming 10 keys for different services (e.g., API Back-End, Payment Processing, Database Layer).

| Configuration Item           | Details                   |
|------------------------------|---------------------------|
| Total Number of Crypto Key Versions | 60                |
| Total Number of Key Use Operations | 60                |
| Total Monthly Cost           | $3.60                     |

### 3.2 Backup and Disaster Recovery in GCP
We set up redundant storage for disaster recovery using multi-region storage.

| Configuration Item           | Details                   |
|------------------------------|---------------------------|
| Location Type                | Multi-region              |
| Location                     | United States (us)        |
| Storage Class                | Standard Storage          |
| Total Amount of Storage      | 10 TiB                    |
| Data Transfer within Google Cloud | Source: North America, Destination: North America |
| Total Monthly Cost           | $471.04                   |

### 3.3 Cloud Spanner with Multi-Region Setup
The configuration for Cloud Spanner with multi-region redundancy ensures high availability.

| Configuration Item           | Details                   |
|------------------------------|---------------------------|
| Service Type                 | Cloud Spanner             |
| Edition                      | Enterprise                |
| Commitment                   | 3 Years                   |
| Number of Nodes              | 2                         |
| Storage Amount               | 1 TB                      |
| Total Monthly Cost           | $1,384.68                 |

### 3.4 Using Cloud Monitoring
If ShopPro International is monitoring 10 VMs with Ops Agent and 5 custom application metrics:

| Field                       | Estimated Value            |
|-----------------------------|----------------------------|
| Volume of Metrics (MiB)     | 300 MiB                    |
| Average Number of Metrics   | 15                         |
| Data Points per Metric per Hour | 60                    |
| Resources                   | 10                         |
| Total Monthly Cost          | $219.95                    |

### 3.5 Using Cloud Logging
Configuration for logging storage and retention:

| Configuration Parameter      | Suggested Value           |
|------------------------------|---------------------------|
| Service Type                 | Cloud Logging             |
| Logging Storage Amount       | 100 GiB                   |
| Logging Retention Duration   | 2 Months                  |
| Monthly Cost                 | $27.00                    |
