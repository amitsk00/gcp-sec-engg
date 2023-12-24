
# Best practises

## GFE

## Cloud Armour

## Load Balancers

# Protection levels

## Data protection

### Governance

### DLP

#### InfoTypes

* Pre Defined - many options are available
* Custom - can be created based on need - like, custom internal mail ID , and then `likelihood` can be attached to each
  * small/regular custom dict
    * use when list is static
    * count can be in thousands
    * e.g. Room Names
  * large/stored custom dict
    * when the list is present in bucket or BQ
    * count can be in millions
    * list of phrases is stored in BQ table or bucket file, and then DLP converts that into a dict file (not editable by users)

  * RegEx

* these types can be of INCLUDE or EXCLUDE category
  * Exclude can be used to reduce the outcome
    Hotword - can be used to increase the likelihood
* These can be RegEx , digits with precision, math checksum or prefixes
* `Likelihood` is returns by API to confirm the same as name suggests

#### Inspection

* Inspection jobs -  You can inspect a BigQuery table, a Cloud Storage bucket or folder, and a Datastore kind
* content.inspect -  method of the DLP API lets you send data directly to the DLP API for inspection
* hybrid job - lets you scan payloads of data sent from any source, and then store the inspection findings in Google Cloud

#### De-Identify

* Create a de-identified copy of Cloud Storage data using an inspection job
* content.deidentify - request to the DLP API

* `dlpJob` to create the job

#### Sensitive Data Protection provides the following method types

* Content methods - data sent directly to API
* Storage methods - data is stored in storage
* Hybrid methods - request starts as COntent method, but results are stored as Storage

### Inspecting and redacting personally identifiable information (PII)

### Configuring pseudonymization

### Configuring format-preserving substitution

### Restricting access to BigQuery, Cloud Storage, and Cloud SQL datastores

## Encryption

## HSM

## Data Masking

<https://cloud.google.com/apigee/docs/api-platform/security/data-masking>

## Infra Security

* DDoS
* Firewalls
* IDS/IPS
* WAF
* Container Security

### Automating virtual machine image creation, hardening, maintenance, and patch management

* For added security, you can also use the Trusted image feature to define an organization policy (ompute.trustedImageProjects) that restricts images in specific public image projects from being used
* startup scripts - to load what you need, but in idempotent way
* The process of creating a custom image is called **baking**.
* Automated baking using Packer
* Enforcing lifecycle policies -
  * --delete-in or --delete-on
  * --obsolete-in or --obsolete-on
* `compute.imageUser` for using images from shared project

### Automating container image creation, verification, hardening, maintenance, and patch management

* NA

### Automating policy as code and drift detection

* `Chekov` from HSBC side
* Codify infrastructure and policies
* automate routine compliance checks
* Automated enforcement - Prevent non-compliance by asserting infrastructure and policies as code for easy onboarding on Google Cloud
* Detect non-compliance via Security Command Center, notifying stakeholders when offending infrastructure is identified.
* Modernize compliance by automating routine checks to reduce your audit fatigue

* Use `IaC` (like Terraform) to detect drift

* Drift -
  * In the context of infrastructure and application management, drift refers to the system state in which the actual configuration and state of the system deviate from the intended or expected configuration and state
  * automated by tools, scripts or services that analyze and compare configurations, resource states or event logs

## Scanning, Logging and Monitoring

* Vuln Scanning
* SIEM

## OS Login

* Manage SSH access to your instances using IAM
* Maintains consistent Linux user identity across VM instances
* Recommended way to manage many users across multiple instances or projects
* Simpliﬁes SSH access management
