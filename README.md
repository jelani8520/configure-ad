# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Setup Domain Controller in Azure,Create a Resource Group,Create a Virtual Network and Subnet
-Setup Client-1 in Azure,Create the Client VM (Windows 10) named “Client-1”,Attach it to the same region and Virtual Network as DC-1,After VM is created, set Client-1’s DNS settings to DC-1’s Private IP address.From the Azure Portal, restart Client-1,Login to Client-1, Attempt to ping DC-1’s private IP address
Ensure the ping succeeded

PowerShell: Azure PowerShell provides automation capabilities for deploying, configuring, and managing virtual machines and other cloud resources efficiently.- Step 

<h2>Deployment and Configuration Steps</h2>




with in azure i created  aomain Controller (DC) a server in a Windows Active Directory (AD) environment that manages user authentication, security policies, and access to network resources. It verifies login credentials, enforces security settings, and controls permissions for users and devices within a domain.  </p>
<br />
<img width="1680" alt="Screen Shot 2025-02-17 at 2 10 47 PM" src="https://github.com/user-attachments/assets/8fc97cf6-a1ee-4ff5-b025-ed19bf355f56" />

<p>
 within active directory tools i conntected client 1  to the domain controller and created users to use for viewing  tasks active directory  provides several tools for managing users, such as Active Directory Users and Computers (ADUC) for creating, modifying, and organizing user accounts, groups, and permissions. Group Policy Management (GPMC) helps enforce security policies and settings across users and devices. Active Directory Administrative Center (ADAC) offers a modern interface for managing accounts efficiently. PowerShell enables automation of user management tasks, like bulk account creation and modification 

</p><img width="1680" alt="Screen Shot 2025-02-12 at 7 40 29 AM" src="https://github.com/user-attachments/assets/1052e7a2-c1b4-4397-8b46-4fd5868e4892" />
Active Directory Users and Computers (ADUC) is a Microsoft Management Console (MMC) snap-in used to manage users, groups, computers, and organizational units (OUs) in a Windows Active Directory (AD) environment. It allows IT admins to create, modify, delete, and organize users and computers within a network.

<img width="1680" alt="Screen Shot 2025-02-17 at 2 15 35 PM" src="https://github.com/user-attachments/assets/bb5ccfb6-c8ac-44a8-8571-d5c8fe037f84" />

<p>
as i added them to the Remote Desktop Users group via Active Directory Users and Computers (ADUC) or the Local Users and Groups tools i then procced to  update Group Policy (GPO) to allow RDP connections by enabling "Allow log on through Remote Desktop Services" in gpedit.msc under Security Settings. Ensure the firewall allows RDP (port 3389) and check that Network Level Authentication (NLA) is configured. For security, limit access to administrators and necessary users only.</p>
<br />
<img width="1680" alt="Screen Shot 2025-02-17 at 2 29 21 PM" src="https://github.com/user-attachments/assets/1c3866a2-f6e6-49bf-ad7e-19eb34107ea3" />
Active Directory Domain Services (AD DS) is the core component of Microsoft Active Directory (AD) that manages user authentication, access control, and network resources in a Windows domain environment. It allows administrators to create and manage users, groups, computers, and policies within an organization.
Key Functions of AD DS:
User Authentication: Verifies user credentials for logging into domain-joined computers.
Centralized Management: Controls access to files, printers, and applications across the network.
Group Policy Management: Enforces security policies and configurations on user accounts and devices.
Single Sign-On (SSO): Allows users to access multiple resources with a single login.
Hierarchy & Organization: Uses domains, organizational units (OUs), forests, and trees to structure resources.
<p><img width="1680" alt="Screen Shot 2025-02-17 at 2 47 23 PM" src="https://github.com/user-attachments/assets/2d17f0c4-959a-4cd7-83f6-88cf21a34343" />
add users to the Remote Desktop users group and configure rep permissions via group policy, enable Remote Desktop on the domain joined computers, open rdp port in windows defender firewall, test Remote Desktop connection 
 <img width="1680" alt="Screen Shot 2025-02-17 at 3 16 28 PM" src="https://github.com/user-attachments/assets/81391d40-e43c-43c2-9798-f6fd978140a6" />
To configure password lockout rules in Group Policy Management (GPO) for a Windows Active Directory domain, open Group Policy Management (gpmc.msc) and navigate to Default Domain Policy or create a new GPO. In the Group Policy Editor, go to Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Account Lockout Policy and configure settings such as Account lockout threshold (failed attempts before lockout), Account lockout duration (how long the account stays locked), and Reset account lockout counter (time after which failed attempts reset). A recommended setup is 5 failed attempts, a 15-30 minute lockout duration, and a 15-minute reset period to balance security and usability. Apply changes using gpupdate /force and verify with gpresult /r. To monitor lockout events, check Event Viewer (eventvwr.msc) under Windows Logs > Security, specifically event ID 4740. Proper configuration helps prevent brute-force attacks while minimizing user inconvenience. 
<img width="1680" alt="Screen Shot 2025-02-17 at 3 46 14 PM" src="https://github.com/user-attachments/assets/e0b3ff2f-bba0-4c3c-8df4-4be12a441aa9" />
after configuring rules i was able to make password lockout setting and log back in to a users account
<p><img width<img width="1680" alt="Screen Shot 2025-02-17 at 4 03 36 PM" src="https://github.com/user-attachments/assets/b12bb496-f24f-4b25-bab7-fd8d4dd8adea" />
i was able to log back in and id the computer 
 <img width="1680" alt="Screen Shot 2025-02-17 at 4 05 49 PM" src="https://github.com/user-attachments/assets/d3ae5ac8-3945-41c6-a165-cb75cf76c1cc" />

</p>
<br />
