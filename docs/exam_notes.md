# test exam wise


## IAM

* Group create/edit permissions are managed by Workspace and not by IAM
* etag is for concurrency checks - good practise to use them when updating policy so that overwrites can be avoided


## xx

* SSO and GCDS are mutually exclusive


## KMS
* KEK never leaves KMS
* encryption is AES256
* The process is the same for GMEK or CMEK
* For CSEK (GCS and GCE Only) the primary difference is the KEK is always supplied directly by the customer. Specified in the boto config file

* **--destroy-scheduled-duration**  - this flag can be set only while creating the key, and can't be changed later



## VPC

### Shared VPC
* good security segmentation as only Network User role is ennugh
* centralized network management
* only within same Org


### VPC Peering
* can be across Org too
* needed on both sides (at subnet level) - each network has its own Network Admin
* high throughput and low latency (unlike VPN)



## counts

* Each Allow policy can have 1500 principals
* Each Allow policy can have 250 domains or Groups















