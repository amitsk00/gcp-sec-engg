# test exam wise


## xx

* SSO and GCDS are mutually exclusive


## KMS
* KEK never leaves KMS
* encryption is AES256
* The process is the same for GMEK or CMEK
* For CSEK (GCS and GCE Only) the primary difference is the KEK is always supplied directly by the customer. Specified in the boto config file



## VPC

### Shared VPC
* good security segmentation as only Network User role is ennugh
* centralized network management
* only within same Org


### VPC Peering
* can be across Org too
* needed on both sides (at subnet level) - each network has its own Network Admin
* high throughput and low latency (unlike VPN)