# Security

## Access Context Manager

<https://cloud.google.com/access-context-manager/docs/access-control>
<https://cloud.google.com/sdk/gcloud/reference/access-context-manager/perimeters/update>

* User + Device + Context is the new security perimeter
* Devcie type and OS + IP + user Identity

### Made up of

* Access Policy -
  * it has levels and perimeters
  * Policy can be at Org or Folder or Project level

* Access levels - its collection of conditions - like, device type, IP, ID

* IP Address
  * single Access Level can have multiple IP ranges
  * Access Levels **cannot include** private IP ranges (for example, 192.168.0.0/16, 172.16.0.0/12).

* Device Type - This would include OS and verion too

* User Identity -




* Workload Identity = used when microservices deployed to your GKE cluster need to access other GCP resources / APIs.
* Workload Identity Federation = when some services of yours deployed outside of GCP (in on-premises or other hyperscalers) need to access GCP resources / APIs.

## Apigee Security

* Automated API Security with ML based abuse detection
* Key Functionalities: Advanced API Security focuses on two key areas:
  * Identifying API Misconfigurations: It simplifies the process of finding API proxies that violate security standards, saving time for API teams.
  * Detecting Bots: It can effectively detect bots that successfully exploit APIs and return a 200 OK response, indicating successful data access.
* Fully managed comprehensive solution to build, manage, and secure APIs—for any use case or scale
* Managing high value/volume of APIs with enterprise-grade security and dev engagement
* Implement security in multiple layers with advanced controls
  * Better protect your web apps and APIs against threats and fraud with Google Cloud
  * Google Cloud WAAP can be used to protect applications on Google Cloud and on-premises
  * Google Cloud Web App and API Protection (WAAP)
    * Cloud Armor protects against DDoS attacks and common web application vulnerabilities (OWASP 10), and is WAF
    * Apigee manages API keys , enforces quotas , validates OAuth tokens and provides analytics on API trends
    * reCAPTCHA Enterprise protects against bot attacks

## Cert Authority

* Simplify the deployment, management, and security of your enterprise PKI
* Customize Certificate Authority Service to your needs by
  * configuring custom CAs and certificates
  * Custom key sizes and algos
  * enforcing granular access controls (with IAM and VPC SC)
  * automating common tasks with APIs
  * integrating with your existing systems
* Have peace of mind knowing that your CA service is highly available, scalable, backed by an SLA, auditable, and ready to help you achieve compliance with advanced hardware and software security controls
* Help lower your total cost of ownership and simplify licensing with pay-as-you-go pricing and zero capital expenditures
* Have confidence that your CAs are approved as part of ISO 27001, 27017, 27018, SOC1, SOC2, SOC3, BSI C5, and PCI DSS.
* `CA Pool` allows rotation seamless as no disruption by adding new cert in pool and revoking old one

## Signed URL / Policy for GCS

* SA to have access to GCL
* signed URL to have access to anyone, temp basis
* Signed Policy Documents (UTF 8 and base64 encoded) specify what can be uploaded to a bucket with a form POST
* Allow greater control over size, content type, and other upload characteristics than signed URLs.

## OAuth

<https://cloud.google.com/apigee/docs/api-platform/security/oauth/oauth-home>

## Security Command Center

* Identify security misconfigurations and vulnerabilities in your Google Cloud environment and resolve them with actionable recommendations
* Uncover threats with specialized detectors
* Threat prevention - Uncover misconfigurations
* Threat detection
* Attack path simulation
* Duet AI
* SIEM and SOAR integrations

* Continuous exports findings work only for newly created findings.
* Continuous exports to Pub/Sub are usually used for forwarding findings to external security management systems such as Splunk or QRadar.
  * Pub/Sub can be created from Console
  * BQ is created using `gcloud scc bqexports create`

* Made up of
  * Container Threat Detection
  * Event Threat Detection
  * Rapid Vulnerability DetectionPreview
  * Secured Landing Zone servicePreview
  * Security Health Analytics
  * Virtual Machine Threat Detection
  * Web Security Scanner


## Context aware  Access [here](https://cloud.google.com/access-context-manager/docs/overview)  

* to define fine-grained, attribute based access control for projects and resources
* This only defines policy, its enforced by others like VPC SC/IAP/IAM Conditions
* Access Policy is made up of
  * Access Levels
  * Service Perimeters

* made up of Access Level which is
  * Device type, operating system and version 
  * IP address (can't include private IP ranges)
  * User identity

```
gcloud access-context-manager policies create \
--organization ORGANIZATION_ID [--scopes=SCOPE] --title POLICY_TITLE
```  



## Intrusion Detection System [here](https://cloud.google.com/security/products/intrusion-detection-system?hl=en)

* Easy deployment and minimal upkeep
  * Network-based threat detection
  * Cloud-native and managed
* Backed by industry-leading threat research ( built with Palo Alto Networks’ threat detection technologies)
  * Industry-leading security breadth and efficacy
* Supporting customers’ compliance goals
* Integrates with Chronicle (security analytics platform), SIEM and SOAR
* If using Shared VPC, single IDS can support multiple proj using shared VPC
* IDS Enpoint is a zonal resource which monitors 
* uses *Packet Mirroring* based on
  1. subnet - all instances in t
  2. tags - upto 5 tags are allowed
  3. individual VM - upto 50 
* Each IDS instance can capable of inspecting traffic in a single region
  1. it peers google network
  2. creates 3 VM on Google nextwork for IDS
  2. Private Service Access is a link between VPC and mirrored VPC
  2. packet mirroring and logs are used by this
* This is needed for PCI DSS and HIPAA



### Configuring and monitoring Security Command Center (Security Health Analytics, Event Threat Detection, Container Threat Detection, Web Security Scanner)



### Identity Aware Proxy IAP

### Cloud Asset Inventory

### Web Security Scanner
