#  Configuring access within a cloud solution environment



## Managing Cloud Identity. Considerations include:

### Configuring Google Cloud Directory Sync and third-party connectors

### Managing a super administrator account

### Automating the user lifecycle management process

### Administering user accounts and groups programmatically




## Managing service accounts. Considerations include:

### Protecting and auditing service accounts and keys

### Automating the rotation of user-managed service account keys

### Identifying scenarios that require service accounts

### Creating, disabling, authorizing, and securing service accounts

### Managing and creating short-lived credentials

### Configuring workload identity federation

### Securing default service accounts

### Managing service account impersonation





## Managing authentication. Considerations include:

### Creating a password and session management policy for user accounts

### Setting up Security Assertion Markup Language (SAML) and OAuth

### Configuring and enforcing two-factor authentication



## Managing and implementing authorization controls. Considerations include:

### Managing privileged roles and separation of duties with Identity and Access Management (IAM) roles and permissions

### Granting permissions to different types of identities

### Managing IAM and access control list (ACL) permissions

### Designing identity roles at the organization, folder, project, and resource level

### Configuring Access Context Manager

### Applying Policy Intelligence for better permission management

### Managing permissions through groups



## Defining resource hierarchy. Considerations include:

### Creating and managing organizations

### Managing organization policies for organization folders, projects, and resources

### Using resource hierarchy for access control and permissions inheritance






# Configuring perimeter and boundary security



## Designing perimeter security. Considerations include:

### Configuring network perimeter controls (firewall rules, hierarchical firewalls, Identity-Aware Proxy [IAP], load balancers, and Certificate Authority Service)

### Identifying differences between private and public addressing

### Configuring web application firewall (Google Cloud Armor)

### Configuring Cloud DNS security settings




## Configuring boundary segmentation. Considerations include:

### Configuring security properties of a VPC network, VPC peering, Shared VPC, and firewall rules

### Configuring network isolation and data encapsulation for N-tier application design

### Configuring VPC Service Controls




## Establishing private connectivity. Considerations include:

### Designing and configuring private connectivity between VPC networks and Google Cloud projects (Shared VPC, VPC peering, and Private Google Access for on-premises hosts)

### Designing and configuring private connectivity between data centers and VPC network (IPsec and Cloud Interconnect)

### Establishing private connectivity between VPC and Google APIs (Private Google Access, restricted Google access, Private Google Access for on-premises hosts, Private Service Connect)

### Using Cloud NAT to enable outbound traffic




# Ensuring data protection


## Protecting sensitive data and preventing data loss. Considerations include:

### Inspecting and redacting personally identifiable information (PII)

### Configuring pseudonymization

### Configuring format-preserving substitution

### Restricting access to BigQuery, Cloud Storage, and Cloud SQL datastores

### Securing secrets with Secret Manager

### Protecting and managing compute instance metadata




## Managing encryption at rest, in transit, and in use. Considerations include:

### Understanding use cases for Google default encryption, customer-managed encryption keys (CMEK), customer-supplied encryption keys (CSEK), Cloud External Key Manager (EKM), and Cloud HSM

### Creating and managing encryption keys for CMEK, CSEK, and EKM

### Applying Google's encryption approach to use cases

### Configuring object lifecycle policies for Cloud Storage

### Enabling Confidential Computing

### Encryption in transit








# Managing operations within a cloud solution environment



## Building and deploying secure infrastructure and applications. Considerations include:

### Automating security scanning for Common Vulnerabilities and Exposures (CVEs) through a continuous integration and delivery (CI/CD) pipeline

### Automating virtual machine image creation, hardening, maintenance, and patch management

### Automating container image creation, verification, hardening, maintenance, and patch management

### Automating policy as code and drift detection





## Configuring logging, monitoring, and detection. Considerations include:


### Configuring and analyzing network logs (firewall rule logs, VPC flow logs, packet mirroring, Cloud Intrusion Detection System [Cloud IDS])

### Designing an effective logging strategy

### Logging, monitoring, responding to, and remediating security incidents

### Exporting logs to external security systems

### Configuring and analyzing Google Cloud audit logs and data access logs

### Configuring log exports (log sinks and aggregated sinks)

### Configuring and monitoring Security Command Center (Security Health Analytics, Event Threat Detection, Container Threat Detection, Web Security Scanner)















# Supporting compliance requirements


## Determining regulatory requirements for the cloud. Considerations include:


### Determining concerns relative to compute, data, and network

### Evaluating the security shared responsibility model (Access Transparency)

### Configuring security controls within cloud environments (regionalization of data and services)

### Limiting compute and data for regulatory compliance

### Determining the Google Cloud environment in scope for regulatory compliance



