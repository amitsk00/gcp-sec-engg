

## Access Context Manager 

https://cloud.google.com/access-context-manager/docs/access-control
https://cloud.google.com/sdk/gcloud/reference/access-context-manager/perimeters/update

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
