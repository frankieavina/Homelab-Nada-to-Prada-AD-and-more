[← Back to main README](../README.md)

# Part 6: Joining PCs to the Domain

Now that the domain controller is up and running, we can join our two Windows 11 client PCs to the `homelab.local` domain.

## Point the Client's DNS to the Server

Before a client can find and communicate with the domain, it needs to use the domain controller as its DNS server (since AD relies on DNS to locate domain resources).

1. Open **Control Panel** → **Network and Sharing Center**.
2. Click **Ethernet** → **Properties**.
3. Double-click **Internet Protocol Version 4 (TCP/IPv4)**.
4. Change the **Preferred DNS server** to the IP address of the domain controller.

## Join the Domain

1. Open **File Explorer** → right-click **This PC** → **Properties**.
2. Click **Change settings** next to the computer name (or "Workgroup or domain name").
3. Click **Change...**.
4. Under **Member of**, select **Domain** and type the domain name: `homelab.local`.
5. Click **OK**. When prompted, enter the credentials of an account with permission to join computers to the domain — for example, `Administrator` and the domain controller's admin password.
6. Restart the computer to complete the join.

## Verify the Computer Joined Successfully

1. On the domain controller, open **Server Manager** → **Tools** → **Active Directory Users and Computers**.
2. Expand the domain (`homelab.local`) → click **Computers**.
3. The newly joined PC should now appear in this container.

Repeat this whole process for the second client PC.

---
