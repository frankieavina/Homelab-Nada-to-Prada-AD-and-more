[← Back to main README](../README.md)

# Part 5: Configuring DNS and Promoting the Domain Controller

## Set the DNS Suffix and Domain Name

1. Right-click **This PC** (or go to **System Properties**) → **Computer Name** → **More**.
2. Enter the primary DNS suffix — this will be our domain name: `homelab.local`.

## Create a Forward Lookup Zone

A **zone** is the namespace reserved for a set of DNS records — essentially, where DNS stores the name-to-IP mappings for our domain. A **forward lookup zone** specifically stores hostname-to-IP-address mappings, so when a computer asks DNS for the IP of a server, DNS looks inside this zone and returns the correct address.

1. Go to **Tools** → **DNS**.
2. Expand your server's name in the left pane.
3. Right-click **Forward Lookup Zones** → **New Zone**.
4. Set the zone name to match your domain: `homelab.local`.
5. Select **Allow both nonsecure and secure dynamic updates**.

## Promote the Server to a Domain Controller

1. Click the flag/notification icon in **Server Manager**.
2. Click **Promote this server to a domain controller**.
3. Select **Add a new forest** and enter your domain name (`homelab.local`).
4. Click **Install** and let the server restart.

**Result:** The server is now a fully functioning Active Directory domain controller for the `homelab.local` domain.

---
