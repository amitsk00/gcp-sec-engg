# test exam wise

[quiz link](https://www.cloudskillsboost.google/course_sessions/2971352/quizzes/376102)


## counts

* Each Allow policy can have 1500 principals - including duplicates
* Each Allow policy can have 250 domains or Groups





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

* SA keys
  * chance of leakage
  * can't be tracked / audited
  * no expiration date and hence pose a risk

??? note

    Ditch the keys and use Workload Identity & Workload Identity Federation!

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

### Best Practises

* Use Custom VPC as Auto mode has same ranges and all routes created (not least privileged)
  * Auto mode VPC can't be peered as they have same CIDR ranges
* sensitive or regulated data (like PCI DSS, HIPAA etc) should be put into separate VPC
* Cloud Interconnect to join on-prem network
  * 2 GCP VPC in IC would have more latency as request routes through on-prem
* Create a shared services VPC if multiple VPC networks need access to common resources but not each other
* To secure a network, add VPC SC
* Isolate VMs using service accounts when possible
  * Using SA is preferred over tags as changing this is tougher
* Use automation to monitor security policies when using tags

* `Cloud Healthcare API` to remove personally identifying information (PII) and protected health information (PHI) from Digital Imaging and Communications in Medicine

### Shared VPC

* good security segmentation as only Network User role is ennugh
* centralized network management
* only within same Org

### VPC Peering

* can be across Org too
* needed on both sides (at subnet level) - each network has its own Network Admin
* high throughput and low latency (unlike VPN)

---

* Network Anomaly needs header and payload info, so only VPC Flow logs are not enough, we need **Packet Mirroring**

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

## Load Balancer

* SYN flood attacks - A SYN flood (half-open attack) is a type of denial-of-service (DDoS) attack (at Layer 4) which aims to make a server unavailable to legitimate traffic by consuming all available server resources

## Notes

* In case of logs routing to GCS - bucket access needs to be fine-graned
* SA can't write to target sink if target sink/BQ's project doesn't have Billing Account associated with it
* One can't delete log bucket if there is linked BQ dataset
* WAF - Web Application Firewalls
  * CSP service, appliance, or plugin, that applies a WebACL (ruleset) to an HTTP/S connection
* DAST - Dynamic AST (blck box)
  * DAST is used against applications in their running state
  * effective when testing exposed HTTP and HTML interfaces of web applications
  * Due to the nature of SAST being a white-box test tool, ``SAST typically delivers more comprehensive results`` than those found using DAST
* SAST - Static Application Security Testing (white box)
  * analysis of the application source code, byte code, and binaries is carried out by the application test without executing the code
  * earlier in the development lifecycle
  * Can be used to find SQL injection attacks, cross-site scripting errors, buffer overflows, and unhandled error conditions
* Vendor lock-in - cant move to another CSP because of some constraint
* Vendor lock-out - stuck with CSP which has gone bankrupt or out of business
* **HA VPN over InterConnect** is beneficial as it can be set using Console or CLI, and can also use private IP ranges

## Doubts

* Which of the following is always available for the disposable of electronic records within a cloud environment?




## Check in Console

* BQ Authorized view and dataset
* Firewall Insights
* Web Security Scanner
