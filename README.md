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
<blockquote>Create a new virtual machine by clicking on "New" in VirtualBox, naming it "Domain Controller," and selecting the "Windows Server 2022" ISO file as the boot media: </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/CD95XTq.png" height="80%" width="80%" alt="VirtualBox New"/>
<br />
<blockquote>Right-click the newly created virtual machine and press settings, configure two network adapters: one for connecting to the internet and the other for the private network:  </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/GXSXYLI.png" height="80%" width="80%" alt="Network Adapters"/>
<br />
 <img src="https://i.imgur.com/1d9CCI1.png" height="80%" width="80%" alt="Network Adapters"/>
<br />
<blockquote>Install Server 2022 on the virtual machine, determine which NIC serves as our NAT and assign IP addressing for the internal network: </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/CMWC282.png" height="80%" width="80%" alt="Network Config"/>
<br />
  <img src="https://i.imgur.com/EI6mVUB.gif" height="80%" width="80%" alt="IP Properties"/>
 <br />
<blockquote>In Server Manager click Add roles and features and install "Active Directory Domain Serivces": </blockquote> <br/>
<p align="center">
<img src="https://i.imgur.com/HCNsYIl.png" height="80%" width="80%" alt="Server Manager"/>
<br />
  <img src="https://i.imgur.com/RPyi7lt.png" height="80%" width="80%" alt="AD Install"/>
<br />
<blockquote>Use Active Directory Domain Services Wizard to promote this server to domain controller and name the domain:  </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/ip5zvwE.png" height="80%" width="80%" alt="AD domain controller"/>
<br />
<blockquote>In Server Manager again, Add roles and features and install Remote Access so that clients on the private network can access the internet through the domain controller: </blockquote> <br/>
<p align="center">
<video src="https://private-user-images.githubusercontent.com/50858187/320340303-adc8cf60-1c6c-46e7-ac9c-d459afc4f579.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjkxMDUyNjUsIm5iZiI6MTc2OTEwNDk2NSwicGF0aCI6Ii81MDg1ODE4Ny8zMjAzNDAzMDMtYWRjOGNmNjAtMWM2Yy00NmU3LWFjOWMtZDQ1OWFmYzRmNTc5Lm1wND9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNjAxMjIlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjYwMTIyVDE4MDI0NVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTViM2Y4YjQxNzdmZjJjMjkwNDNiMjBhNzAwMjRlNDFkMGRlYjhjNWMxZjg3NWRlNDJlNmM0MmM4ZWM5Y2FmNTUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.b_1e_vOWZtpbGBehncpHjGBxTisuY5_bdDTjnBDW9Uw" height="80%" width="80%" alt="Remote Access"/> </video>
<br />
 <p align="center">
 <blockquote>With the role successfully installed, the next step is to configure the Routing and Remote Access functionality</blockquote> <br/>  
 <p align="center">
<video src="https://private-user-images.githubusercontent.com/50858187/320340465-90498c51-c780-4776-a80e-3a97b725edc4.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjkxMDU2ODgsIm5iZiI6MTc2OTEwNTM4OCwicGF0aCI6Ii81MDg1ODE4Ny8zMjAzNDA0NjUtOTA0OThjNTEtYzc4MC00Nzc2LWE4MGUtM2E5N2I3MjVlZGM0Lm1wND9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNjAxMjIlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjYwMTIyVDE4MDk0OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTlkMmI4NTAzMjJhMTM0ZWFiN2RiMmJiZjY0Yjc3MmEyMGRiODNkZjEyZDJiZDU3NTBkODk5NTlmZjhiYjBkMzMmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.laZhN5vsX60eHMaIDNc-BC-oaRGiVZbja3D7H_OMBtg" height="80%" width="80%" alt="Remote Access"/> </video>
<br />
  <p align="center">
<blockquote>  With Remote Access installed and configured, it's time to proceed with installing a DHCP Server. This step will facilitate the assignment of IP addresses to our Windows clients, enabling them to browse the internet seamlessly:  </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/2K7IEI8.gif" height="80%" width="80%" alt="DHCP"/>
<br />
<blockquote> Now, let's configure the DHCP and establish a scope. DHCP's primary function is to automatically assign IP addresses to computers on the network. The scope I'm creating will allocate IP addresses within the range of 192.168.1.100 to 192.168.1.200, providing DHCP the capability to assign 100 IP addresses effectively: </blockquote> <br/>
<p align="center">
<video src="https://private-user-images.githubusercontent.com/50858187/320340524-2dbc7973-868f-4e64-b29c-d68acf537345.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjkxMDY2MzEsIm5iZiI6MTc2OTEwNjMzMSwicGF0aCI6Ii81MDg1ODE4Ny8zMjAzNDA1MjQtMmRiYzc5NzMtODY4Zi00ZTY0LWIyOWMtZDY4YWNmNTM3MzQ1Lm1wND9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNjAxMjIlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjYwMTIyVDE4MjUzMVomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWU0NTQzMTBmNmM5YzJiYmZhYWRjNGEwMzg0YjY4MGFjZTgwYjk1ODIwMDBhNjEwYWE1NTExMmZmODJmOWZmNTAmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.KfqWXOFETm59cdU5qhnUNcTf9HftnnEACe1zgzwitFE" height="80%" width="80%" alt="DHCP"/></video>
<br />
<blockquote> With Active Directory and my Domain Controller properly configured, run the PowerShell script to populate your userbase: </blockquote><br/>
<p align="center">
<video src="https://private-user-images.githubusercontent.com/50858187/320340597-def52115-f57e-4330-be61-7812c973580e.mp4?jwt=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3NjkxMDY5NDcsIm5iZiI6MTc2OTEwNjY0NywicGF0aCI6Ii81MDg1ODE4Ny8zMjAzNDA1OTctZGVmNTIxMTUtZjU3ZS00MzMwLWJlNjEtNzgxMmM5NzM1ODBlLm1wND9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNjAxMjIlMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjYwMTIyVDE4MzA0N1omWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPWEyNjJhZGQ5ZmFhNTk0NmMxYzg5ZGE2M2Y3NmY5ZDk1ODU2ZTQzYjZkNWY2NDkzNGE0YmYyNTk1NWYyMzM4MWUmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0In0.DERbduQQ8NptTJ0LcyQ3GG2B0g6OMqy7S11pFvmPXJw" height="80%" width="80%" alt="ps1"/></video>
<br />
<blockquote> Now it's time to create a client which will function as a user's workstation within the domain. Back in VirtualBox, press new, set up a Windows 11 VM with the ISO and name it CLIENT: </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/XEOMIQr.png" height="80%" width="80%" alt="CLIENT"/>
<br />
<blockquote> In the client settings, change its network adapter to Internal Network: </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/13wtjhL.png" height="80%" width="80%" alt="CLIENT"/>
<br />
<blockquote> Connect the client machine to the private network, verify if the client VM is correctly receiving the assigned IP address from the DC, and join it to the domain. The purple square confirms that I have been successfully leased an IP address by the domain controller. Additionally, the green square highlights successful pinging of the domain, indicating proper connectivity: </blockquote><br/>
<p align="center">
<img src="https://i.imgur.com/sHrP4an.png" height="80%" width="80%" alt="CLIENT"/>
  <br />
<img src="https://i.imgur.com/MTFUeE1.png" height="80%" width="80%" alt="CLIENT"/>
    <br />
<blockquote> You can now log into the client machine with one of the accounts created by the PowerShell script! </blockquote><br />
<p align="center">
  <img src="https://i.imgur.com/UFOAQeF.gif" height="80%" width="80%" alt="CLIENT"/>
 <br />
 <blockquote>Finally, you may return to the server VM, and review the DHCP to assess the number of leased addresses. As highlighted, it's evident that the "CLIENT1" Virtual Machine has been assigned an address. In a real corporate setting, this folder would likely contain hundreds, if not thousands, of leased addresses, depending on the lease duration.</blockquote><br/>
 <p align="center">
 <img src="https://i.imgur.com/1dRYpxF.png" height="80%" width="80%" alt="CLIENT"/>
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
