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

To first set up this lab I created two Virtual Machines(VMs) within Azure that were on the same virtual network to ensure that the two VMs could communicate with one another. One VM was created with Windows 10 while the other was created with Linux(Ubuntu). Using command line/PowerShell I will connect the Ubuntu VM to the Windows VM.

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 05 48 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/548f7728-5f6c-4ff2-88e6-774ee8d1e6a3">
</p>
<p>
Using Remote Desktop Connection, I connected to the Windows VM using its public IP address. From there, I installed Wireshark to begin inspecting traffic.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 09 13 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/2fe03e2a-81eb-4b5e-bd73-33c19378dc4f">
</p>
<p>
starting up Wireshark I see a lot of traffic flood the screen from there I will start to filter it to only show icmp(Internet Control Message Protocol) traffic. To filter it out I will just go to the "Apply a display filter" bar and just type icmp. I will then open PowerShell to use the ping command which utilizes icmp to communicate the data transmission that the two VMs. And by getting the private IP of the Ubuntu VM we can observe the request and replies within Wireshark on the Windows VM. 
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 12 45 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/59db8661-56a5-41cf-9d26-8c99c3cacfeb">
<img width="700" alt="Screen Shot 2023-07-23 at 1 15 42 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/ad145a1e-431f-41c6-a032-0f97cc151b72">
</p>
<p>
I used a perpetual ping to the Ubuntu VM in order to see how network security groups work. I activated the perpetual ping by using the command: ping -t (ip address). This caused Wireshark to be spammed with icmp traffic so to counteract that I enter Azure portal and open the networking settings for the Ubuntu VM and created a new inbound port rule to deny all icmp traffic while also setting the priority above all preset inbound port rule. 

Returning to the Windows VM I will see the ping in Powershell reply with "request timed out" assuring that the new inbound port rule is working. Heading back to Azure portal I will switch the port rule to allow the icmp traffic once again and I will see the traffic coming from the Ubuntu VM on the Windows VM. To exit the perpetual Ping within Powershell I will just click Control C to stop all communication.  
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 22 33 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/b20fab88-31a6-4732-8411-1aa273c1b37a">
</p>
<p>
Next, I will observe SSH traffic. On Wireshark I will filter for ssh traffic by using tcp.port==22 no traffic will be shown at the moment. Entering Powershell I will log in to the Ubuntu VM by using the command ssh@(username ip address). SSH traffic will start to be shown on Wireshark and with each command I use within the Powershell Ubuntu VM ssh connection the more ssh traffic that can be observed. I once again close the command with "control c".
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 25 15 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/21dbc726-2b1c-42cc-8390-566e5460fb4b">
</p>
<p>
I then moved on to examine dhcp traffic. To observe this traffic I used the command ipconfig /renew on Powershell to issue the Window VM a new IP address. This command may result in losing connection to the VM for a brief second but once back in I will be able to observe the resulting traffic.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 26 56 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/5666f834-a61f-420f-8e34-fbbcb60e02e5">
</p>
<p>
After observing dhcp traffic I wanted to examine dns so by typing udp.port == 53 into the filter I will only be able to see the dns traffic on Wireshark. And to see dns traffic I'll utilize the nslookup command on Powershell to look up the ip address of popular sites like google.com and disney.com.
</p>
<br />

<p>
<img width="700" alt="Screen Shot 2023-07-23 at 1 28 46 PM" src="https://github.com/angelmartinez4147/azure-network-protocols/assets/131706484/8b9ea2bb-af59-443a-8e00-fd8ff74c104d">
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
