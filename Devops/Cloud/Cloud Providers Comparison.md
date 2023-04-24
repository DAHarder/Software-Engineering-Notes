| AWS                   | Azure                                                                 | Google Cloud Platform                                         |
|-----------------------|-----------------------------------------------------------------------|---------------------------------------------------------------|
| Account               | Subscription                                                          | Project                                                       |
| N/A                   | Management Group                                                      | Folder                                                        |
| N/A                   | Resource Group                                                        | N/A                                                           |
| ALB                   | Azure Application Gateway or                                          | Google Cloud Load Balancing or                                |
|                       | ELB’s Gloo Edge Helm Chart                                            | ELB’s Gloo Edge Helm Chart                                    |
| Network Load Balancer | Azure Load Balancer                                                   | Load Balancer                                                 |
| Direct Connect        | ExpressRoute                                                          | Interconnect                                                  |
| Private Link Service  | Private Link Service                                                  | Private Service Connect                                       |
| EBS                   | Azure Managed Virtual Disk                                            | Persistent Disk                                               |
| EC2                   | Virtual Machine                                                       | Compute Engine                                                |
| EC2 Autoscaling       | Virtual Machine Scale Sets (VMSS)                                     | Compute Engine Autoscaler                                     |
| EKS                   | Kubeadm Control Plane clusters with VMSS (Virtual Machine Scale Sets) | Kubeadm Control Plane clusters with Compute Engine Autoscaler |
| Elasticache           | Azure Cache for Redis                                                 | Memorystore for Redis                                         |
| KMS                   | Azure Key Vault                                                       | Cloud Key Management                                          |
| MSK                   | Confluent Cloud cluster                                               | Confluent Cloud Cluster                                       |
| RDS                   | Azure Database for MySql/PostgreSQL Flexible server                   | Cloud SQL (MySQL/PostgreSQL)                                  |
| S3                    | Storage account                                                       | Cloud Storage                                                 |
| S3 Bucket             | Azure Storage Container                                               | Cloud Storage Buckets                                         |
| SQS                   | Azure Storage Queues                                                  | Cloud Tasks                                                   |
| VPC                   | VNET                                                                  | VPC                                                           |
| NAT Gateway           | NAT Gateway                                                           | Cloud NAT                                                     |
| VPC Security Groups   | VNet Network Security Group (NSG)                                     | VPC Service Controls                                          |
