<p align="center">
<img src="https://imgur.com/wYucC7L.png" alt="osTicket logo"/>
</p>

<h1>Microsoft Azure Compute and Networking 🪟 - Observe DHCP (Dynamic Host Configuration Protocol) Traffic</h1>
Using the DHCP Protocol, I release and then renew the IP Address of the Windows 10 Virtual Machine. <br />

<h2>Environments and Technologies Used</h2>

- Lenovo Ideapad 5 Pro 16gb AMD Ryzen 7
- Microsoft Azure Resource Group (from [Part 1 - Setting Up Virtual Machines](https://github.com/cyberwahid01/2.1-Virtual-Machine-Setup))
- Microsoft Azure Windows 10 Pro version 22H2 - x64 Gen2 Virtual Machine (from [Part 1 - Setting Up Virtual Machines](https://github.com/cyberwahid01/2.1-Virtual-Machine-Setup))
- Microsoft Azure Ubuntu Pro 24.04 LTS - x64 Gen2 Virtual Machine (from [Part 1 - Setting Up Virtual Machines](https://github.com/cyberwahid01/2.1-Virtual-Machine-Setup))
- Wireshark Network Protocol Analyzer Software
- Windows Powershell

<h2>Operating Systems Used </h2>

- Local Windows 11 Home Version 21H2</b>
- Windows 10 Pro version 22H2 Virtual Machine
- Ubuntu Pro 24.04 LTS - x64 Gen2 Virtual Machine

<h2>List of Prerequisites</h2>

- Microsoft Azure Subscription
- Microsoft Azure Subsription Credit
- Wireshark Installed on Windows 10 Virtual Machine

<h2>Installation, Setup, Resource Setup, Executing Functions</h2>

1. I started off initialising packet capture within Wireshark and filtered for DHCP traffic. As we can see nothing is showing as I have not 
<p>
<img src="https://imgur.com/oVLJybo.png" alt="Disk Sanitization Steps"/>
</p>
<p>
2. In this example, I had to run a dhcp.bat file which contained the release and renew commands for this protocol. Please read below for a breakdown of what is happening during this process. 
</p>
<br />

<p>
<img src="https://imgur.com/jIrYgHu.png" alt="Disk Sanitization Steps"/>
</p>
<p>
3. This sequence represents a DHCP (Dynamic Host Configuration Protocol) process, showing a device obtaining an IP address. Here’s a brief breakdown:

1297 - DHCP Release:
IP 10.0.0.4 informs the DHCP server (168.63.129.16) that it is releasing its IP address, making it available for others.

1315 - DHCP Discover:
A new device (0.0.0.0) broadcasts to 255.255.255.255 to find a DHCP server, initiating the process to request an IP.

1316 - DHCP Offer:
The DHCP server (168.63.129.16) responds with an IP offer and other configuration details, referencing the same transaction ID (0xeb864ec4).

1317 - DHCP Request:
The device requests the offered IP, confirming its acceptance of the configuration.

1318 - DHCP ACK:
The DHCP server acknowledges the request and assigns the IP address to the device, completing the DHCP process.

This sequence shows the typical four-step DORA process: Discover, Offer, Request, Acknowledge, with an additional Release step at the start.
