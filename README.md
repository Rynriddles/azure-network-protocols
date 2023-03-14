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

- Step 1: Create a Windows 10 virtual machine and an Ubuntu server in Azure.
- Step 2: Download wireshark within the windows 10 machine. Ping the ubuntu server and observe the traffic from within wireshark.
- Step 3: Observe SSH traffic and DHCP traffic.
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/MVvUTBD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first thing that we do is create a virtual machine running windows 10 and a virtual machine running the ubuntu server. After those are created, we then check to make sure that they are on the same network. 
</p>
<br />

<p>
<img src="https://i.imgur.com/xlaQq3X.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/0uzuXtG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After we remote into the windows machine, we download wireshark. Wireshark is a network tracking tool that lets you observe traffic on your network. We can use the filter option to filter by ICMP traffic. We then ping the ubuntu machine and we observe the traffic coming through within wireshark. We can also ping public websites (such as google.com) and observe that traffic within wireshark. (Ubuntu server traffic top picture, google.com traffic bottom picture)
</p>
<br />

<p>
<img src="https://i.imgur.com/kvByeGM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/lgEKb5c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
We can filter wire shark for other kinds of traffic as well. DNS or domain name service is a service that associates the name of a website with its IP address. This is a very helpful service as website names are a lot easier to remember than IP addresses are. Additonally, computers are unable to read website names and can only understand IP addresses. This service bridges the gap between human logic and computer logic. We are able to filter this within wireshark much like ICMP traffic (top picture). Wireshark also allows us to filter for DHCP (dynamic host configuration protocol). The DHCP protocol is the protocol that assigns each computer its own IP address when it connects to the network (bottom picture). 
</p>

<p>
<img src="https://i.imgur.com/2ovmatf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/Bz1j0Au.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Azure comes with various network security features. We are able to filter certain traffic within our virtual machines by using the networking options within Azure. We are going to block ICMP traffic within our ubuntu machine. We will be able to see within wireshark that our machine is requesting information, but it is not receiving anything in return. This is because the traffic is being blocked by the firewall on the ubuntu machine.
</p>

<br />
