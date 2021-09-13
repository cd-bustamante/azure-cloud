# Azure VM

## Availability sets

Protecting againts planned and unplanned outages

- Fault Domain (common source of failure) avaialable hosts in Azure Datacenter
- Update Domain (platform updates) available hosts in Azure Datacenter.

VM has to be created in the same resource group and location as the Availability set.

More than one VM to get SLA of 99.95%

## Scale Sets

Consistently scale your solution to meet demand

- Clear definiition of what a VM in your solution is and how it is configured (size, OS, NICs, image, etc)
- Rules which determine when and why your solution will scale in and out.
  - Autoscale Definition
    - Condition: when/why autoscale will trigger
    - Direction: scale-in or scale-out
    - Response: action to occur +1 or -1 instance
  - Autoscale Scale-In Policy
    - VM deletion priority during scale-in. By default:
      - VMs balance across Availability Zone
      - VMs balance across Fault Domains
      - Vms with the highest ID deleted first

Evaluation order

1. Fixed date profile
2. Ocurrence profile
3. Regular profile

## Dedicated Hosts

- Physical host infrastructure which is not share with others
- You have control over maintenance (patching and reboots)
- Helps meet compliance requirements
- Great to take advantage to your existing software license agreements (you can apply your existing license per host, so all your VM or Containers on that host can use the same license)

## Azure Disk Encryption

Encryption of data on Managed Disk volumes, data is encrypted between the OS and the managed disk.

- It is required a VM extension, it supports:
  - Windows using Bitlocke
  - Some Linux distributions using DM-Crypt
- Relies on Key Vault storing encryption information (stores encryption key)
- Encryption of boot (OS) and data volumes

