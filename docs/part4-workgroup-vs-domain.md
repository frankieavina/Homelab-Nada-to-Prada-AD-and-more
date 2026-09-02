g[← Back to main README](../README.md)

# Part 4: Workgroup vs. Domain, and Installing AD DS

## Workgroup vs. Domain

- **Workgroup:** Every computer operates independently. There's no central authority managing users or resources — each machine manages its own local accounts and permissions.
- **Domain:** A centralized network management model. A **domain controller** manages authentication, users, and resources for every device joined to the domain, using **Active Directory**.

## Prepping the Server

Before installing AD, the server's own DNS setting needs to point back to itself (this is required since the server will also be acting as the DNS server):

1. Go to **Ethernet** → **Properties** → **IPv4**.
2. In the **DNS** field, enter the server's own IP address.

## Installing AD DS

1. Open **Server Manager** → **Manage** → **Add Roles and Features**.
2. Click **Next** through the wizard, select **Role-based or feature-based installation**.
3. Select your server from the server pool.
4. Choose **Active Directory Domain Services**.
5. Click **Install**.

## Installing DNS

1. Open **Server Manager** → **Manage** → **Add Roles and Features**.
2. Select **DNS Server**.
3. Click **Install**.

---
