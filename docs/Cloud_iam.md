
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

* Allow policy
  * Principal
  * Role
  * Condition - optional
  * etag - for consistency checking
  * version
* Deny policy
  * name : policies/ATTACHMENT_POINT/denypolicies/POLICY_ID
  * uid
  * kind
  * etag
  * displayName
  * createTime
  * updateTime
  * deniedPrincipals
  * exceptionPrincipals: Optional
  * deniedPermissions
  * Deny takes precedence over Allow

1. principal requests an access
2. system first checks Deny policy
    1. if access is denied (present in Deny policy), deny the request
    2. else (missing in Deny policy), go further
3. system checks for Allow policy
    1. if access is given (present in Allow policy), access is granted
    2. else (missing in Allow policy), access is denied

## GCDS

* Roles needed to start with
  * DNS Admin
  * external IdP Admin
  * future Admin of GCP Org

* Steps to be taken:
  * Sign up for Cloud Identity or Google Workspace. During the sign-up process, you must provide a contact phone number and email address, the primary domain that you want to use, and the username for the first super-admin user account.
  * Verify the ownership of your primary domain by creating either a TXT or CNAME record in the corresponding DNS zone of your DNS server.
  * Add any secondary domains to the Cloud Identity or Google Workspace account.
  * Verify ownership of the secondary domains by creating either TXT or CNAME records in the corresponding DNS zones of your DNS server.
  * Protect your account by configuring security settings.
  * Create a default configuration for user accounts
* OU are not needed if ext IdP is being used
* OU specific for Google Workspace can be used as some settings can't be applied to groups and hence OU may be needed
  
* Azure AD:
  * CReate new OU in GCP - only for this reason
  * create new use to access Azure AD and add in this new OU
  * new user must be super-admin so that all user management is possible

* In Azure portal, create new App as Google Cloud
  * In Attributes, map UPN Source as `mail`
  * From User Settings, all or some groups can be setup

* Then, Azure AD SSO is needed for auth
* Configure `SAML` for this  
  * Uisng Manage > SSO > SAML
  * provide reply and sign-on URL paths
  * Download SAML Signing Cert
  * For `Uniq User ID` use source as Mail
* COnfigure Google WOrkspace for SSO
  * Open `Admin Console` and login as super-admin
  * Security > Auth > SSO with 3rd party IdP
  * Add URL for Sign-on, Sign-out and change=password (as setup previously on Azure AD)
  * For Verification Cert, upload prev downloaded cert (from Azure AD)

* Main GCDS tasks:
  * It reads for LDAP, and using `Directory API` laods into Cloud Identity
  * for on-prem AD, its best to run GCDS on-prem
  * This process has sensitive info (and hence should remain within local network)
  * LDAPS (LDAP + SSL) or Cloud VPN can be used to encrypt the data
  * There needs a user on GCP side, with super-admin privs
  
