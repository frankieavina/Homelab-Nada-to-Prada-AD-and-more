# Homelab: Building an Active Directory Environment

This repo documents my journey setting up a home lab to learn Active Directory (AD) administration. It covers everything from spinning up virtual machines to promoting a server to a domain controller and configuring DNS.

## Overview

The goal of this lab is to simulate a small business network with a Windows Server domain controller and two Windows 11 client machines, all running as virtual machines on a single host. This gives hands-on experience with core Windows Server administration skills, including Active Directory Domain Services (AD DS), DNS, and domain networking.

## Prerequisites

- A Windows host machine with enough CPU, RAM, and disk space to run multiple VMs
- VMware Workstation (Pro or Player)
- ISO files for:
  - Windows Server 2025
  - Windows 11 Pro

## Guide Sections

| Part | Topic |
|------|-------|
| [Part 1](docs/part1-vm-setup.md) | Setting Up the Virtual Environment |
| [Part 2](docs/part2-static-ip.md) | Assigning a Static IP to the Server |
| [Part 3](docs/part3-connectivity.md) | Establishing and Testing Connectivity |
| [Part 4](docs/part4-workgroup-vs-domain.md) | Workgroup vs. Domain, and Installing AD DS |
| [Part 5](docs/part5-dns-promotion.md) | Configuring DNS and Promoting the Domain Controller |
| [Part 6](docs/part6-joining-pcs.md) | Joining PCs to the Domain |
| [Part 7](docs/part7-ous-and-gpo.md) | Creating and Managing OUs, Users, and Group Policy |

## Next Steps

Future additions to this lab may include:

- Setting up file shares and NTFS/share permissions
- Creating security and distribution groups
- Delegating administrative control over OUs
- Exploring DHCP configuration on the server
