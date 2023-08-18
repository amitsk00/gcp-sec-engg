

### IPv6

* only IPv6 isnt supported
* single stack for IPv4
* dual stack for IPv4 and IPv6
*  /48 ULA range within fd20::/20 is assigned if enabled on VPC
* VM gets /96 range from subnet
    * VM inherits IPv6 access type (internal or external) from subnet
* dual stack not supported on auto mode or legacy networks


### Routes

* applies for egress (from VM)
* System generated
* Custom
* Peering based

