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
- Create an Admin and Normal User Account in AD
- Join Client-1 to your domain
- Setup Remote Desktop for non-administrative users on Client-1
- Create additional users and attempt to login Client-1 with one of the users

<h2>Deployment and Configuration Steps</h2>

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
<img src="https://i.imgur.com/JkHLSUC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Login to the Domain Controller through the Remote Desktop Connection and enable ICMPv4 on the local Windows Firewall.  To do this go to Start-->Windows Administrative Tools-->Windows Defender Firewall with Advanced Security
</p>
<br />

<p>
<img src="https://i.imgur.com/m9W0gaQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the Windows Defender menu click on Inbound Rules-->Click on Protocol to ascend the types-->Look for ICMPv4 protocol-->Right Click on echo requests and Enable Rule.  This will now allow the clients DNS server to establish connection with the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/NuJNMKK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To confirm connectivity, Open an instance of your client desktop and open your command prompt-->type ping -t and the private Ip address-->enter.  If a connection has been established between, this command will ping the specified host continuously until stopped. The host is replying so we have an established a successful connection between the client and the host.
</p>
<br />

<h3>Install Active Directory</h3>
<p>
<img src="https://i.imgur.com/5JTXYCf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open an instance of your Domain Controller from the Remote Desktop Connection and open the server manager.  Click on Add roles and features.  The following steps will install Active Directory on this server.
</p>
<br />

<p>
<img src="https://i.imgur.com/n8YIEe5.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Add roles and features and the wizard will open.  Click on next a couple of times until you see your destination server to connect.  Click next a few times again until you see the Select server roles.  Check the radio button Active Directory Domain Services.  On that page, click on Add Features. Click on next through the proceeding pages that installs all of the dependencies and the final install button.
Click Add roles and features and the wizard will open.  Click on next continually until you see your destination server to connect.  Click next a few times again until you see the Select server roles.  Check the radio button Active Directory Domain Services.  On that page, click on Add Features. Click on next through the proceeding pages that installs all of the dependencies and the final install button.
</p>
<br />

@@ -183,7 +183,7 @@
<img src="https://i.imgur.com/EXKhRiA.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the group box is populated, type "domains" in enter the object names to be selected box-->Click on Check Names to the right-->Select Domain Admins-->Click Ok-->Click on Apply-->Click Ok. This will add your user as a domain admin to your active directory. Log out of the server and log back into the server as the admin.
Once the group box is populated, type "domains" enter the object names to be selected box-->Click on Check Names to the right-->Select Domain Admins-->Click Ok-->Click on Apply-->Click Ok. This will add your user as a domain admin to your active directory. Log out of the server and log back into the server as the admin.
</p>
<br />

@@ -230,12 +230,6 @@
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
<h3>Create additional users and attempt to login Client-1 with one of the users</h3>
<p>
