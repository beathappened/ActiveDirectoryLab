<h1>Active Directory Home Lab</h1>

<h2>Description</h2>
In this lab we're going to walk through how to create an Active Directory home lab Environment using Oracle VirtualBox. Configuring and running this lab will develop your understanding of how Active Directory and Windows networking works.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b> 
- <b>Oracle VirtualBox</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (21H2)
- <b>Server 2019</b> 


<h2>Network Diagram:</h2>
<br/>
<p align="center">
<img src="https://i.imgur.com/5F86IV5.jpeg" height="80%" width="80%" alt="Network Diagram"/>
<br />
<br />

<h2>What You'll Need:</h2>
<a href= https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019> Server 2019 Iso</a href> <br/>
<a href= https://www.microsoft.com/en-us/software-download/windows10> Windows 10 ISO</a href>
<br/>
<a href= https://www.virtualbox.org/wiki/Downloads> Oracle VirtualBox</a href>
<br/>
<a href= "https://github.com/joshmadakor1/AD_PS">PowerShell Script to Populate Userbase</a href>
<h2>Set Up walk-through:</h2>

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
