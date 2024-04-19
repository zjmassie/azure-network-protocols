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

- Create Resource Groups In Azure
- Create Virtual Networks & Subnets
- Create Virtual Machines (Windows & Linux)
- Create Network Security Groups
- Use Wireshark & Command Line Tools
- Observe Network Traffic

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/04954ad3-e04e-43f3-8bea-29b6b9c35ded)"/>
</p>
<p>
Create a resource group within Azure, this will house both virtual machines that will be created.
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/30071c88-3f0d-4bed-957f-0cdf32319d4f)"/>
</p>
<p>
Create the first virtual machine using Windows 10.
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/d46e9a4d-e77c-4734-a08e-21113829bce6)"/>
</p>
<p>
Create the second virtual machine using Linux. Note: make the authentication type a password instead of SSH public key.
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/df169d44-3409-4256-b1b3-21b44fdd4277)"/>
</p>
<p>
Remote Desktop into Virtual Machine 1 (VM1) using public IP address.
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/981e5181-aaa3-488b-9b22-b9648f69541d)"/>
</p>
<p>
Download & install Wireshark (run as admin).
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/129d9356-33a3-4184-b3b4-1d1095bfaede)"/>
</p>
<p>
Use Powershell (or cmd line) to observe different types of traffic between VM1 (Windows) and VM2 (Linux) in Wireshark. Seen here: ICMP traffic. 
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/b1799bee-9b4c-4193-8b0c-3f26ff573f3b)"/>
</p>
<p>
To observe firewall protocols on VM2, begin "perpetual ping" from VM1.
</p>
<br />

<p>
<img src="https://github.com/zjmassie/azure-network-protocols/assets/139398375/64949edf-8393-4b47-a4d2-3c6741d7b7b5)"/>
</p>
<p>
In Azure, navigate to Network Security Group for VM2 (Linux). Add a new Inbound Security Rule that denies ping traffic. Observe the changes in Wireshark in VM1. Back in Azure, set the Inbound Security Rule back to "allow" (or delete the rule).
</p>
<br />

<p>
Done.
</p>
<p>
Note: Make sure to clean up your Virtual Machines in Azure!
</p>
