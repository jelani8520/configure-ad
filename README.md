# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
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

- Azure Virtual Machines support Remote Desktop Protocol (RDP), allowing users to securely access and manage VMs from anywhere.

-Active Directory Domain Services (AD DS): Azure AD DS enables centralized authentication, user management, and policy enforcement for cloud and hybrid environments.

PowerShell: Azure PowerShell provides automation capabilities for deploying, configuring, and managing virtual machines and other cloud resources efficiently.- Step 

<h2>Deployment and Configuration Steps</h2>


<p><img width="1680" alt="Screen Shot 2025-02-10 at 8 33 42 PM" src="https://github.com/user-attachments/assets/78ab46bf-7a12-402f-9a44-9774f82071f1" />

with in azure i created  aomain Controller (DC) a server in a Windows Active Directory (AD) environment that manages user authentication, security policies, and access to network resources. It verifies login credentials, enforces security settings, and controls permissions for users and devices within a domain.  </p>
<br />

<p>
 within active directory tools i conntected client 1  to the domain controller and created users to use for viewing  tasks active directory  provides several tools for managing users, such as Active Directory Users and Computers (ADUC) for creating, modifying, and organizing user accounts, groups, and permissions. Group Policy Management (GPMC) helps enforce security policies and settings across users and devices. Active Directory Administrative Center (ADAC) offers a modern interface for managing accounts efficiently. PowerShell enables automation of user management tasks, like bulk account creation and modification 

</p><img width="1680" alt="Screen Shot 2025-02-12 at 7 40 29 AM" src="https://github.com/user-attachments/assets/1052e7a2-c1b4-4397-8b46-4fd5868e4892" />

<p>
as i added them to the Remote Desktop Users group via Active Directory Users and Computers (ADUC) or the Local Users and Groups tools i then procced to  update Group Policy (GPO) to allow RDP connections by enabling "Allow log on through Remote Desktop Services" in gpedit.msc under Security Settings. Ensure the firewall allows RDP (port 3389) and check that Network Level Authentication (NLA) is configured. For security, limit access to administrators and necessary users only.</p>
<br />

<p>

<p><img width="1680" alt="Screen Shot 2025-02-12 at 7 36 30 AM" src="https://github.com/user-attachments/assets/e5701108-ab00-45da-9116-0e328f86f2ee" />
 Assigning users to security groups and distribution lists for permission control. 



</p>
<br />
