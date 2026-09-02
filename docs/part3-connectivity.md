[← Back to main README](../README.md)

# Part 3: Establishing and Testing Connectivity

Before installing AD, we need to make sure the server and both client PCs can actually reach each other on the network.

1. Note the IP address of both client VMs (same process as Part 2, steps 1–3).
2. Turn off the firewall on both client PCs:
   - **Control Panel** → **System and Security** → **Windows Defender Firewall** → **Turn Windows Defender Firewall on or off**
   - Select **Turn off Windows Defender Firewall** for all three profiles (Domain, Private, Public).
3. Repeat the same firewall steps on the server.
4. Test connectivity between machines using `ping` (e.g., ping each client's IP from the server, and vice versa).

> **Note:** Disabling the firewall entirely is fine for a lab environment, but in a production setting you'd instead create specific inbound/outbound rules.

---
