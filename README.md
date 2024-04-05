<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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

- Creating VM's (Windows 10 & Linux/Ubuntu)
- Observe ICMP Traffic
- Observe SSH Traffic
- Observe DHC Traffic
- Observe RDP Traffic
- Observe DNS Traffic
- Obserev DHCP Traffic

<h2>Actions and Observations</h2>

<p>
  
- Creating your VM's

  -Create a windows 10 virtual machine

  -Create a linux/Ubuntu virtual machine
  
   


  
  


<img src="https://i.imgur.com/Ay09qbO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<img src="https://i.imgur.com/zHUPDRM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

-While creating the Linux/Ubuntu VM be sure to chose the same vnet (Virtual Network) as the windows 10 VM

<img src="https://i.imgur.com/OG4yZPv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>




- Observe ICMP traffic
  
  -Remote desktop into the windows 10 virtual machine and while in the VM download and install wireshark

  -Open WireShark and filter for ICMP traffic

  -Go into VM-2 (Linux/Ubuntu) and retrieve its private ip address and attepmt to ping it from within the Windows 10 VM.

  -View the request and replys between VM-1 and VM-2 within WireShark after pinging VM-2


  <img src="https://i.imgur.com/nVbPCBB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


  -In VM-1 using PowerShell attempt to ping googles public ip address and observe the traffic within WireShark


 

  <img src="https://i.imgur.com/NZJSBOD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  -Within Azure go to VM-2's NetWork Security Group and disable all inbound ICMP traffic and Observe request the time outs in WireShark and PowerShell between VM-1 and VM-2

  <img src="https://i.imgur.com/ROsI1hc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <img src="https://i.imgur.com/8xjtjfx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  -Enable inbound ICMP Traffic back in VM-2's NetWork Security Group and observe the succsessful ping in WireShark And PowerShell

    <img src="https://i.imgur.com/QGLxwsU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


- Observe ICMP traffic

   -In WireShark filter for SSH traffic
  
  -In VM-1 SSH into VM-2 VIA its private address

  1.Type commands usernames, pwd, exc. into the linux SSH connectionand observe the traffic in WireShark.

  <img src="https://i.imgur.com/eQ6GWj1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
    <img src="https://i.imgur.com/QGLxwsU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

    -Exit the SSH connection by typing exit and pressing enter

  
  
- Observe DHCP Traffic
 
  -In WireShark filter for DHCP traffic
  
  -In VM-1 attempt to issue you VM a new IP address using command line (ipconfig/renew)
  
  1.View the traffic activity in WireShark

  <img src="https://i.imgur.com/2G7760k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Observe DNS Traffic
 
    -In WireShark filter for DNS traffic
  
    -While in VM-1 using command prompt or PowerShell use nslookup to see what google.com and disney.com's IP addresses are 

  <img src="https://i.imgur.com/qOAoCV6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

- Observe RDP Traffic

   -In WireShark filter for RDP traffic(tcp.port==3389)
  
   -Observe the constant traffic because of the RDP filter

  <img src="https://i.imgur.com/eQ6GWj1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>


  








  





   


