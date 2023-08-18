

### Workload Identity
* Google Cloud provides service accounts to act as identities for workloads

1. Attached servcie accounts - using this workload can access GCP services
2. short lived token/creds - OAuth2 or OIDC token for SA
3. GKE Workload Identity - GKE SA can act as IAM SA adn access GCP servcies

* Workload identity federation: Use credentials from external identity providers to generate short-lived credentials, which workloads can use to temporarily impersonate service accounts. Workloads can then access Google Cloud resources, using the service account as their identity.
* Service account keys: Use the private portion of a service account's public/private RSA key pair to authenticate as the service account.





* Cloud Identity or Google Workspace accounts
    * OU
        * For Org, OU can be created to group users and create hierarchies
        * OU help to assign rules at top level
        * user : OU :: 1:1
        * user : Group :: 1:many
        * OU shudn't be used to manage acess - Groups are meant for access
    * Managed User Account
        * managed by Admin
        * primary email is ID, but can have aliases and recovery mail IDs
    * Groups
        * identified with mail ID - but need not be linked to mailbox
        * nesting of groups is allowed
    * External identities
        * using existing external ID and creds, using IdP
        * setting up SSO using SAML
        * this needs a user in GCP IAM which is identified by external users mail ID
        * GCP account : SAMP IdP :: 1:1
        * Commonly used external IdPs include Active Directory Federation Services (AD FS), Azure AD, Okta, or Ping Identity
    * External authoritative source
    * External user account
    * External group
    
* Federated user identities - use external creds to federate on GCP
* Federation using Cloud Identity or Google Workspace - external ID uses External ID Provider (IdP) to access GCP. GCP also has ID for the same user - pref with same mail ID. GCDS or AD can be used to synch up IDs
* Workforce identity federation - can use IdP to auth group of users, **no need** to synch/GCDS


## IdP

* The maximum size for attribute mappings is 4 KB.
