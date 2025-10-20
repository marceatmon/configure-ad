<p align="center">
<img src="https://github.com/marceatmon/AD-files/blob/main/Active%20DirectoryLogo3.png" alt="osTicket logo"/>
</p>

<h1>Active Directory: Installing and Configuring Active Directory within Azure VMs</h1>
This tutorial outlines the prerequisites and installation of Active Directory.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Deployment and Configuration</h2>

- Create Two Virtual Machines
- Ensure Connectivity between the client and Domain Controller
- Install Active Directory

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Setting%20up%20Client%20VM.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Microsoft Azure, create two virtual machines. Create a Domain Controller (DC-1) using Windows Server and a Client PC (Client-1) using Windows 10 Pro.
</p>
<br />

<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Remote%20Dekstop.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open remote desktop connection and create two instances for the domain controller and the client.  You will need this to create connectivity between the two in the next step.
</p>
<br />

<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Changing%20Domain%20Controller%20IP%20from%20Dynamic%20to%20Static.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In Azure, change the assignment of the private IP address from dynamic to static so the IP address will stay the same for client's DNS to connect to the server.
</p>
<br />

<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Checking%20DNS%20Server%20in%20PowerShell.jpg?raw=true?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the Microsoft Azure dashboard, restart and log into Client-1. Open PowerShell and ping DC-1’s private IP address by running the "ipconfig /all" command. DC-1’s private IP Address should show in the DNS Settings.
</p>
<br />

<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Logged%20into%20Domain%20Controller%20using%20Remote%20Desktop.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to the Domain Controller through the Remote Desktop Connection and enable ICMPv4 on the local Windows Firewall.
</p>
<br />


<p>
<img src="https://github.com/marceatmon/AD-files/blob/main/Installing%20Active%20Directory%20onto%20Domain%20Controller.jpg?raw=true" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To install Active Directory, open the Domain Controller from the Remote Desktop Connection and open the Server Manager. Click on Add roles and features. Click to add roles and then add features. Continue clicking next until you reach the server roles. Enable Active Directory Domain Services and click Add Features. Continue clicking next until you reach the Install button.
