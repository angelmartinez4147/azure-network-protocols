<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

Observe the following
- ICMP Traffic
- SSH Traffic
- DHCP Traffic
- DNS Traffic
- RDP Traffic
<h2>Actions and Observations</h2>

To first set up this lab I created two Virtual Machines(VMs) within Azure that were on the same virtual network to ensure that the two VMs could communicate with one another. One VM was created with Windows 10 while the other was created with Linux(Ubuntu). Using command line/PowerShell I will connect the Ubuntu VM to the windows VM.

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 09 13 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/2fe03e2a-81eb-4b5e-bd73-33c19378dc4f">
<img width="700" alt="Screen Shot 2023-07-23 at 1 12 45 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/59db8661-56a5-41cf-9d26-8c99c3cacfeb">
<img width="700" alt="Screen Shot 2023-07-23 at 1 15 42 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/ad145a1e-431f-41c6-a032-0f97cc151b72">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 22 33 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/b20fab88-31a6-4732-8411-1aa273c1b37a">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 25 15 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/21dbc726-2b1c-42cc-8390-566e5460fb4b">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 26 56 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/5666f834-a61f-420f-8e34-fbbcb60e02e5">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 28 46 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/8b9ea2bb-af59-443a-8e00-fd8ff74c104d">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
