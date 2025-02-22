# VulnerabiltyManagementProject

### [Pictoral Walkthrough Demonstration]

   In this lab we are going to be doing a vulnerability management lab using Tenable along with Azure VM. But first I want to 
   explain what is a Vulnerablity Management and what it is used for. Vulnerability management is the cyclical practice of 
   identifying, classifying, remediating, and mitigating" software vulnerabilities. Businesses use vulnerability management to help
   reduce organizational risk by modifying sofeware vulnerabilites discovered in a production enviornment. A vulnerability is a 
   weakness exploitable by attackers to to compromise systems or date like a) Out of date 3rd party software (ie; Firefox etc.) 
   b)Out of date OS (ie Windows Updates; etc) c)Misconfigurations (No passwards, airdrop being open)

   <h2>Tools Used</h2>

- <b>Azure</b> 
- <b>Tenable</b>
- <b>Powershell</b>

<h2>Environments Used </h2>
- <b>Windows 10</b> (21H2)
- <b>Azure Virtual Machine</b> 
- <b>Tenable Vulnerability Management</b>
 

<h2>Program walk-through:</h2>
<p align="center">
   Creating a VM in Azure <br/>
<img src="https://imgur.com/Ml4PjjB.png" height="80%" width="80%" "/>
<p align="center"> To being with we want to create a VM. And as part of settings remember to create a resource, which a like a folder for the components that we will use. Name the VM and also create a user name and password for our VM. Also we want to 
create a place the VM within a virtual network. If you dont have one create one. Also we want to use Windows 10 as the VM image we are going to working within. Then create and deploy your VM. <br/>
 
<br />


<p align="center">
   Logging into the VM <br/>
<img src="https://imgur.com/26LYUje.png" height="80%" width="80%" "/>
<p align="center"> The next thing that we want to do is log into our VM that we have created. Click the name of your VM and 
                  then copy the public IP address of your VM. We are going to use this along with your username and password
                  to remote into our VM. Then on your local machine open RDP, then put in the public ip address of your VM 
                  along with your username and password. We need to do a few things to prepare for a scan. <br/>
 
<br />

<br />


<p align="center">
   Windows Firewall the VM <br/>
<img src="https://imgur.com/xueR7rr.png" height="80%" width="80%" "/>
<p align="center"> While in the VM we are looking to disable the Windows firewall. When you have access to the Windows VM
                   go to the start button and type in wf.msc. This will open the Windows Firewall. Then click the Windows 
                   Defender Firewall Properties link.  Turn off the Fire state in the domain profile,private profile, and public
                   profile. Then apply and OK.<br/>
 
<br />

<p align="center">
   Powershell <br/>
<img src="https://imgur.com/qlqedbY.png" height="80%" width="80%" "/>
<p align="center"> Next within the VM go to the start open the Powershell app. We want to import a script into Powershell that 
                   will permit us to scan the this VM remotely. 
                    [Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System"-Name 
                    "LocalAccountTokenFilterPolicy -Value 1 -Type DWord -Force] <br/>. After you have import in the script 
                     enter and restart the VM.
 
<br>

<br />

<p align="center">
    Next, let's create a Vulnerability Managment Scan in Tenable  <br/>
<img src="https://github.com/user-attachments/assets/d9c3019e-930a-4b3c-92f0-6cb4cc061f6d".png" height="80%" width="80%" "/>
<p align="center"> Tenable Vulnerability Management is used as the main operating interface and the Tenable Scan Engine is used 
                   to target and scan Microsoft Azure virtual machines. So once we have created a Tenable account we need to 
                   target the VM that we create in Azure. 
 
<br>

   




   
