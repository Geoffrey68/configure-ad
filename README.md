# configure-ad
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

- Step 1.) Setup Resources in Azure 
<p>
   Create a virtual machine running Windows Server 2022 called DC-1 (domain controller), at the same time create the resource group AD-Lab

<p>
<img src="https://i.imgur.com/6rqEypr.png"/>
</p>
<p>
  
Create a second virtual machine running Windows 10 called Client-1
  
<p>
<img src="https://i.imgur.com/aj8rO2H.png"/>
</p>
<p>
  
Set Domain Controller’s NIC Private IP address to be static
<p>
<img src="https://i.imgur.com/OpSwC3y.png"/>  
</p>
<p>
  
Ensure that both VMs are in the same Vnet DC-1 (you can check the topology with Network Watcher)
  <p>
<img src="https://i.imgur.com/olFgxCi.png"/>  
</p>
<p>
   
- Step 2.) Ensure Connectivity between the client and Domain Controller

<p>
[Video Demonstration of Client-1 to DC-1 connectivity](https://clipchamp.com/watch/tKOiU9sWfKa)
<p>
   
- Step 3.) Install Active Directory
  
<p>
   Login to DC-1 and install Active Directory Domain Services
    <p>
      Open Server Manager, click on Add Roles and Features, select and install ADDS
      <p>
        <img src="https://i.imgur.com/aSuZnGN.png"
</p>
<p>
  Promote as a DC: Setup a new forest as mydomain.com

</p>
<img src="https://i.imgur.com/Z0H2q7C.png"
<br />
- Restart and then log back into DC-1 as user: mydomain.com\labuser
<p>
<img src="https://i.imgur.com/bi7ZVHl.png"/>
</p>
<p>
   
- Step 4.) Create an Admin and Normal User Account in AD
   
   <p>
In Active Directory Users and Computers (ADUC), create an Organizational Unit (OU) called “_EMPLOYEES”, and one called "_ADMINS"
<p>
<img src="https://i.imgur.com/FgVEuzm.png"
<br />
