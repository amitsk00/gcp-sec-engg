# Security

## Access Context Manager 

https://cloud.google.com/access-context-manager/docs/access-control
https://cloud.google.com/sdk/gcloud/reference/access-context-manager/perimeters/update


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

## Cert Authority




## Signed URL / Policy for GCS

* SA to have access to GCL
* signed URL to have access to anyone, temp basis
* Signed Policy Documents (UTF 8 and base64 encoded) specify what can be uploaded to a bucket with a form POST
* Allow greater control over size, content type, and other upload characteristics than signed URLs.


## OAuth

https://cloud.google.com/apigee/docs/api-platform/security/oauth/oauth-home


## Security Command Center


### Configuring and monitoring Security Command Center (Security Health Analytics, Event Threat Detection, Container Threat Detection, Web Security Scanner)
