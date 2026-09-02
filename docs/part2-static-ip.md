[← Back to main README](../README.md)

# Part 2: Assigning a Static IP to the Server

By default, the server gets a DHCP-assigned IP address. We want to convert this to a static IP so it doesn't change, since a domain controller needs a consistent address.

1. Open **Control Panel** → **Network and Internet** → **Network and Sharing Center**.
2. Click on **Ethernet** → **Details**.
3. Jot down the following values (we'll need them in the next step):
   - IPv4 address
   - Default gateway
   - DHCP server
   - DNS server address
4. Go back to **Ethernet** → **Properties** → double-click **Internet Protocol Version 4 (TCP/IPv4)**.
5. Select **Use the following IP address** and enter the IP address, subnet mask, and default gateway you noted above. Enter the DNS server address as well.
6. Confirm the change: the static IP should now appear in **Server Manager** under the **Local Server** → **Ethernet** section.

---
