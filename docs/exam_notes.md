# test exam wise

<https://www.cloudskillsboost.google/course_sessions/2971352/quizzes/376102>

## VM Security

* Confidential VM - the data on VM (in memory) is also protected/secure
  * supported only on *AMD*
  * They have below 2 :
    * Secure Boot is obtained with `UEFI`
      * by verifying the digital signature of all boot components and ending the boot process if signature verification fails
    * Measured Boot is obtained with `vTPM` 
      * helps guard against malicious modifications to the Confidential VM
      * Measured Boot monitors the integrity of a Confidential VM instance's bootloader, kernel, and boot drivers.

* Logging for
  * integrityEvaluationPassed - 
  * sevPolicy - 
  * sevLaunchAttestationReportEvent - ??
  * earlyBootReportEvent - ??


## BQ Security

* Authorized view
  * main table and target view should be in same regional location (but can be in diff datasets)



## IAM

* Group create/edit permissions are managed by Workspace and not by IAM
* etag is for concurrency checks - good practise to use them when updating policy so that overwrites can be avoided

---

* Use Org SSO profiles to set up single sign-on. Using `SAML` profiles is currently incompatible with some Azure AD features, including Azure AD B2B.

* SSO and GCDS are mutually exclusive
* Whenever a user needs to authenticate, Google Cloud delegates the authentication to Active Directory by using the Security Assertion Markup Language (SAML) protocol. This delegation ensures that only Active Directory manages user credentials and that any applicable policies or multi-factor authentication (MFA) mechanisms are being enforced

## KMS

* KEK never leaves KMS
* encryption is AES256
* The process is the same for GMEK or CMEK
* For CSEK (GCS and GCE Only) the primary difference is the KEK is always supplied directly by the customer. Specified in the boto config file

* `--destroy-scheduled-duration`  - this flag can be set only while creating the key, and can't be changed later
* no auto rotation for Asymmetric keys

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

* Each Allow policy can have 1500 principals - including duplicates
* Each Allow policy can have 250 domains or Groups


## Special

The security points are as follows:

* Users:
  * OAuth 2.0
  * IP address access control
* Applications
  * API keys
  * OAuth 2.0
  * TLS
* Developers and partners
  * SSO
  * RBAC
* APIs
  * OAuth 2.0
  * OpenID Connect
  * Quotas
  * Spike arrest
  * Threat protection
* API team
  * IAM RBAC
  * Federated logic
  * Data masking
  * Audit logs
* Backend
  * Private networking
  * Mutual TLS
  * IP address access control

* Use Google Cloud Armor as a WAF layer with Apigee


## From training

* Cloud Security Scanner
* Security Command Center
* Cronicle
* Cloud Armor
* Cert Auth Service
* Web Security Scanner

## DNS

* Can't setup DNS Forwarding to another VPC
* OnPrem must be source or target 
* Uses Google proxies 

* DNS Peering
  * This allows DNS queries to be sennt to another VPC
  * Configure a Zone that is peered to another VPC
  * Then use Pvt Zone, Forwarding Zone or ANS
  * Most useful for SaaS applications

* Mult VPC to OnPrem
  * All but 1 VPC have Peering Zone, which connect to last VPC's Forwarding Zone
  * This Forwarding Zone through InterConnect or VPN goes to OnPrem
  

## Secret Manager

* To add time limit on secret
  * either add expiration time and post that secret is deleted
  * or add IAM with conditions so that access is revoked later


## Check in Console

* BQ Authorized view and dataset
* DLP
* Security Command Center


## Load Balancer

* SYN flood attacks ??