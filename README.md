<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Account
- IIS
- HeidiSQL
- PHP

<h2>Installation Steps</h2>

<p>

<img src="https://i.imgur.com/bDcqfWT.png"/>
</p>
<p>
- To begin the project, we'll start by creating a Windows 11 virtual machine within Azure.
<p></p> - Under resource group, select "create new" and name it "osTicket"
<p></p> - Then we'll name the virtual machine: osTicket-vm
<p></p> - For region select East US 2
<p></p> - Make sure the image is Windows 11 Pro, version 24H2 - x64 Gen2
<p></p> - For the size selct Standard_D2s_v3 - 2 vcpus, 8 GiB memory
<p></p> - The username and password can be whatever you want. Just make sure you remember for when you log into the virtual machine, and then select review + create

</p>
<br />

<p>
<img src="https://i.imgur.com/iIHljOS.png"/>
</p>
<p>
- For the next step, it's time to log into the virtual machine using Remote Desktop/Windows App - free of charge through the app store.
<p></p> - Select + on the upper right corner and select "Add PC" - Then copy osTicket-vm public IP address from Azure, and paste it in PC name.
<p></p> - When prompted, log in with the username and password that you assigned to your virtual machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Once logged into the vm, download the [OSTicket Installation Files](https://drive.google.com/file/d/118z3d-o9Oyom8FgGzbJe2iBiIVB3s1Th/view?usp=sharing)
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

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
