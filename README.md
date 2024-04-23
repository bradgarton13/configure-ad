# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1 Create Two VM's within the same resource group and virtual network. One machine will be a Windows Server 2022 machine(DC1), and the other a Window's 10 machine(Client1).
- Step 2 Connect with DC1 via Remote Desktop and use Server Manager to install Active Directory.
- Step 3
- Step 4
- Step 5

<h2>Deployment and Configuration Steps</h2>

<p>

![image](https://github.com/bradgarton13/configure-ad/assets/166873905/f65a67ba-0e8e-42a0-90ae-44e5de574fd2)


</p>
<p>
I have created the virtual machine DC1 on Microsoft Azure and connected/ logged in to with Remote Desktop. In the image above, I am seen using Server Manager to install Active Directory on the domain controller VM (DC1).  
</p>
<br />

<p>

![image](https://github.com/bradgarton13/configure-ad/assets/166873905/2703dab5-9d27-4629-809b-ce919aa1add5)
![image](https://github.com/bradgarton13/configure-ad/assets/166873905/1b19a068-8c1f-4de2-97ad-b4e86647a6bf)


</p>
<p>
I created two organizational units inside of Active Directory, one being _ADMINS and the other being _EMPLOYEES. I then created a user named jane doe and made her a member of the default group Domain Admins.
  I then changed the DNS server for Client1 to the same address as DC1's private IP address in Azure. This will allow me to move forward with joining Client1 to DC1's domain. I then restarted Client1 and verified my IP address was the same as DC1's private IP (10.0.0.4).
  After that I went into Windows Settings > About Tab > Advanced Settings > Computer Name > Change > and made Client1 a member of DC1's domain (adlabdomain.com).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />



