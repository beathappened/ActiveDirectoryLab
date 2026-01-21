<h1>Active Directory Home Lab</h1>
<h2>Network Diagram:</h2>
<br/>
<p align="center">
<img src="https://i.imgur.com/M5ngW9H.png" height="80%" width="80%" alt="Network Diagram"/>
<br />
<br />
 
<h2>Description</h2>
This project serves as a demonstrative showcase of adept system administration skills, illustrating proficiency in constructing and managing complex network environments. By meticulously configuring a Microsoft Server to host Active Directory and deploying a Domain Controller, the undertaking underscores adeptness in system architecture and domain management.

The utilization of PowerShell scripting to automate user creation processes showcases a nuanced understanding of automation tools, streamlining administrative tasks and enhancing efficiency. Moreover, the successful integration of Windows 11 Enterprise and the Microsoft Server 2022 ISO within a virtualized environment underscores adaptability and proficiency in deploying contemporary technologies.

Through the seamless orchestration of these components, this project not only exemplifies technical expertise but also highlights the ability to navigate and optimize multifaceted IT landscapes, essential traits for effective system administration.
<br />

<h2>Learning Objectives</h2>

 -   Understand the fundamental concepts of Active Directory and its role in network administration
 -   Develop skills in utilizing virtualization software (such as VMWare) to create and manage virtual machines
 -   Learn to set up and manage a Domain Controller within a network infrastructure
 -   Develop problem-solving skills through troubleshooting any issues encountered during the setup and configuration process
 -  Acquire proficiency in using PowerShell scripting to automate administrative tasks within a Windows environment
 -   Understand domain connectivity principles and authentication mechanisms, exemplified through logging into user accounts within a domain environment


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 11 Enterprise</b>
- <b>Server 2022</b> 

<h2>What You'll Need:</h2>
<a href= https://www.microsoft.com/en-us/evalcenter/download-windows-server-2022> Server 2022 </a href> <br/>
<a href= https://www.microsoft.com/en-in/evalcenter/download-windows-11-enterprise> Windows 11 Enterprise</a href>
<br/>
<a href= https://www.virtualbox.org/wiki/Downloads> Oracle VirtualBox</a href>
<br/>
<a href= "https://github.com/joshmadakor1/AD_PS">PowerShell Script to Populate Userbase</a href>
<h2>Lab Walk-through:</h2>

<p align="center">
Create a new virtual machine by clicking on "New" in VirtualBox, naming it "Domain Controller," and selecting the "Windows Server 2019" ISO file as the boot media: <br/>
<img src="https://i.imgur.com/G42Hbhd.png" height="80%" width="80%" alt="VirtualBox New"/>
<br />
<br />
Right-click the newly created virtual machine and press settings, configure two network adapters: one for connecting to the internet and the other for the private network:  <br/>
<img src="https://i.imgur.com/GXSXYLI.png" height="80%" width="80%" alt="Network Adapters"/>
<br />
<br />
 <img src="https://i.imgur.com/1d9CCI1.png" height="80%" width="80%" alt="Network Adapters"/>
<br />
<br />
Install Server 2019 on the virtual machine and assign IP addressing for the internal network: <br/>
<img src="https://i.imgur.com/QXHZFBg.png" height="80%" width="80%" alt="Network Config"/>
<br />
<br />
  <img src="https://i.imgur.com/Nz5WKn6.png" height="80%" width="80%" alt="IP Properties"/>
 <br />
<br /> 
In Server Manager click Add roles and features and install "Active Directory Domain Serivces":  <br/>
<img src="https://i.imgur.com/HCNsYIl.png" height="80%" width="80%" alt="Server Manager"/>
<br />
<br />
  <img src="https://i.imgur.com/RPyi7lt.png" height="80%" width="80%" alt="AD Install"/>
<br />
<br />  
Use Active Directory Domain Services Wizard to promote this server to domain controller and name the domain:  <br/>
<img src="https://i.imgur.com/ip5zvwE.png" height="80%" width="80%" alt="AD domain controller"/>
<br />
<br />
In Server Manager again, Add roles and features and install Remote Access so that clients on the private network can access the internet through the domain controller:  <br/>
<img src="https://i.imgur.com/UQKNo4z.png" height="80%" width="80%" alt="Remote Access"/>
<br />
<br />
In Routing and Remote Access, Right-click the domain controller and install NAT <br/>  
<img src="https://i.imgur.com/ZHSJXNf.png" height="80%" width="80%" alt="Remote Access"/>
<br />
<br /> 
Once more, Add roles and features to install and set up DHCP on the domain controller:  <br/>
<img src="https://i.imgur.com/BMiHy4E.png" height="80%" width="80%" alt="DHCP"/>
<br />
<br />
In DHCP right-click IPv4 and add a new scope: <br/>
<img src="https://i.imgur.com/DPXJTrT.png" height="80%" width="80%" alt="DHCP"/>
<br />
<br />
And configure the default gateway: <br/>
<img src="https://i.imgur.com/TevWYGK.png" height="80%" width="80%" alt="DHCP"/>
<br />
<br />
Run the PowerShell script to populate your userbase:<br/>
<img src="https://i.imgur.com/kint4yq.png" height="80%" width="80%" alt="ps1"/>
<br />
<br />
Now it's time to create a client. Back in VirtualBox, press new, set up a Windows 10 VM with the ISO and name it Client:<br/>
<img src="https://i.imgur.com/OXSdaTX.png" height="80%" width="80%" alt="CLIENT"/>
<br />
<br />
In the client settings, change its network adapter to Internal Network:<br/>
<img src="https://i.imgur.com/13wtjhL.png" height="80%" width="80%" alt="CLIENT"/>
<br />
<br />
Connect the client machine to the private network and join it to the domain:<br/>
<img src="https://i.imgur.com/lh6UWS7.png" height="80%" width="80%" alt="CLIENT"/>
  <br />
<br />
<img src="https://i.imgur.com/MTFUeE1.png" height="80%" width="80%" alt="CLIENT"/>
    <br />
<br />
You can now log into the client machine with one of the created accounts! <br />
  <img src="https://i.imgur.com/f1PQMSX.png" height="80%" width="80%" alt="CLIENT"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
