
# Generic

## Best Practises

* Private clusters 
    * GPA for APIs 
    * NAT for internet
    * Control Plane gets addtional Private Endpoint (no public IP)

* Authorized Networks
    * restrict access to Untrusted Actor the control plane to trusted CIDR ranges
    * Mandatory for private clusters

* Shilded Nodes 
    * by default

* GKE Secrets
    * KMS to manage GKE KEK



## RBAC

* Secure your cluster by granting privileged operations (accessing secrets, for example) only to admin users.
* Enforce user-based authentication and authorization by the cluster.
* Limit resource creation (such as pods, persistent volumes, deployments) to specific namespaces.
* Have users and pods only see resources in their authorized namespace. This allows you to isolate resources
* within your organization (for example, between development teams).

!!! Note  ""

    IAM gives access at project level. RBAC can be used to give access at Cluster or Namespace level

