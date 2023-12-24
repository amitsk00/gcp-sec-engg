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

### Configuring and monitoring Security Command Center (Security Health Analytics, Event Threat Detection, Container Threat Detection, Web Security Scanner)
