# Configuring Active Directory
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Two VM's within the same resource group and virtual network. One machine will be a Windows Server 2022 machine(DC1), and the other a Window's 10 machine(Client1).
- Connect with DC1 via Remote Desktop and use Server Manager to install Active Directory.
- Create a few organizational units inside of Active Directory. Alter Client1's DNS server to be the same as DC1's private IP inside of the Azure Portal. Then, add Client1 to the domain.
- Use a Powershell ISE script to generate 10000 random users apart of the domain and sign into Client1 with one of those users.



<h2>Deployment and Configuration Steps</h2>

<p>

![image](https://github.com/bradgarton13/configure-ad/assets/166873905/f65a67ba-0e8e-42a0-90ae-44e5de574fd2)


</p>
<p>
  
  1. I have created the virtual machine DC1 on Microsoft Azure and connected/ logged in to with Remote Desktop. In the image above, I am seen using Server Manager to install Active Directory on the domain controller VM (DC1).
  
  
</p>
<br />

<p>

![image](https://github.com/bradgarton13/configure-ad/assets/166873905/2703dab5-9d27-4629-809b-ce919aa1add5)
![image](https://github.com/bradgarton13/configure-ad/assets/166873905/1b19a068-8c1f-4de2-97ad-b4e86647a6bf)


</p>
<p>

  2. I created two organizational units inside of Active Directory, one being _ADMINS and the other being _EMPLOYEES. I then created a user named jane doe and made her a member of the default group Domain Admins.
  3. I then changed the DNS server for Client1 to the same address as DC1's private IP address in Azure. This will allow me to move forward with joining Client1 to DC1's domain. 
  4. I then restarted Client1 and verified my IP address was the same as DC1's private IP (10.0.0.4).
  5. After that I went into Windows Settings > About Tab > Advanced Settings > Computer Name > Change > and made Client1 a member of DC1's domain (adlabdomain.com).
  
</p>
<br />

<p>

![image](https://github.com/bradgarton13/configure-ad/assets/166873905/1871c5e4-afef-4d61-a455-6acb063e6960)
![image](https://github.com/bradgarton13/configure-ad/assets/166873905/01add9a0-d0f2-4dc5-8ec7-fa0b6533f1d1)


</p>
<p>
  
6. I then signed into Client1 and went into the Window's settings and navigated to the remote desktop settings in the About tab. I made changed the settings so that any user under Domain Users in the domain can access Client1 remotely. 
7. Using a powershell script I created 1000 users inside of DC1 with the password "Password1". These users were automatically created inside the previously created organization unit "_EMPLOYEES" that we created earlier. 
8. I picked a random user, "caf.jet", and logged into them on Client1 using Remote Desktop with the default given password "Password1". I verified I was on Client1 signed as caf.jet by using the hostname and whoami command in Command Prompt.
  
</p>
<br />


