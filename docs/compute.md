# Compute 

## OS Login


## Confidential VM

* protected by a blend of hardware-grade encryption, memory isolation, and other services that assure workload, data, and platform integrity
* All aspects of a workload are secure even in the event of a physical host breach
* Data at Use is also encrypted with VTPM - only using AMD machines






## Shielded VM


## Boot Integrity

* TPM – module embedded in a system
  * Anchoring the trustworthiness of a system to hardware not software
  * Tamper-resistant security chip installed on the device or built into  PCs, tablets, and phones
  * Stores passwords, certificates, and encryption keys needed to authenticate the platform
* Contributes to Zero Trust for devices and platforms:
  * Integrity (ensures system has not been altered at a low level)
  * Authentication (ensures system is in fact the correct system)
  * Privacy (ensures system is protected from prying eyes)


## DNSSEC

* Domain Name System Security Extensions (DNSSEC) - authenticates responses to domain name lookups
  1. enable at Cloud DNS Zone - Cloud DNS creates and rotates keys auto
  2. TLD - Top Level Domain - DS record to authenticate DNSKEY
  3. DNS Resolver - validates signatures
* In DNSSEC-enabled zones, avoid TTLs longer than 259200 (3 days)
* need to activate at DNS Zone first and then at DNS Registrar (DS record)

