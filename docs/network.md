# Networks  

## Concepts

### IPv6

* only IPv6 isnt supported
* single stack for IPv4
* dual stack for IPv4 and IPv6
* /48 ULA range within fd20::/20 is assigned if enabled on VPC
* VM gets /96 range from subnet
  * VM inherits IPv6 access type (internal or external) from subnet
* dual stack not supported on auto mode or legacy networks

### Routes

* applies for egress (from VM)
* System generated
* Custom
* Peering based

### Connectivity

* Private Google Access (*PGA*)
  * OnPrem/ VM to Google Cloud public API endpoints
  * Products like
    * GCS
    * BQ
    * Pub/Sub
* Private Service Access (*PSA*)
  * OnPrem/VM to Google Services in Google VPC
  * Needs VPC Peering
  * Products
    * CLoud SQL
    * Memcache
    * Cloud IDS
* Private Service Connect (*PSC*)
  * This is better than PSA, as no peering needed
  * single or many Consumer endpoints thru PSC to a single Producer Service attachment
  * Accessible from OnPrem too (without using public IP of PGA)
  * Enables using customer-defined private
endpoints using *.p.googleapis.com
* Follows VPC SC
  * Products like
    * Managed Services:
      * Google APIs
    * Producer VPC
      * Google services
      * 3rd party services
      * Intra-Org servcies
* Serverless VPC Access
  * gets access using VPC Connectors
  * its just /28 MIG on service VPC
  * Products like
    * CLoud Run
    * App Engine standard
    * Cloud Functions

### Network Security

* Configuring network perimeter controls
  * firewall rules
  * Identity-Aware Proxy (IAP)
* Configuring load balancing
  * global
  * network
  * HTTP(S)
  * SSL Proxy
  * TCP Proxy  
* Identifying Domain Name System Security Extensions (DNSSEC)
* Identifying differences between private versus public addressing
* Configuring web application firewall (WAF) (Google Cloud Armor)
* Configuring Cloud DNS

* Network Isolation
  * diff VPC for each need
  * one VPC for on-prem conn (VPN etc)
  * one VPC that allows public internet access
  * one VPC just within Google


## Designing perimeter security. Considerations include

### Configuring network perimeter controls (firewall rules, hierarchical firewalls, Identity-Aware Proxy [IAP], load balancers, and Certificate Authority Service)

### Identifying differences between private and public addressing

### Configuring web application firewall (Google Cloud Armor)

### Configuring Cloud DNS security settings

## Configuring boundary segmentation. Considerations include

### Configuring security properties of a VPC network, VPC peering, Shared VPC, and firewall rules

### Configuring network isolation and data encapsulation for N-tier application design

### Configuring VPC Service Controls

### Designing and configuring private connectivity between data centers and VPC network (IPsec and Cloud Interconnect)

### Using Cloud NAT to enable outbound traffic


### FIrewall Insights

### Packet monitoring
