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
<img src="https://i.imgur.com/26djILq.jpeg"/>
</p>
<p>
- Once logged into the vm, download the OSTicket Installation Files: https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD
<p></p> - Open File Explorer, and drag the downloaded file to the desktop
<p></p> - Then right click on the file and select "Extract All"
</p>
<br />

<p>
<img src="https://i.imgur.com/DfjU4LY.jpeg"/>
</p>
<p>
- Now it's time to install + enbale Internent Information Services (IIS) in Windows with CGI
 <p></p> - Start by selecting the start menu > Type control panel and open it > Navigate to uninstall program under Programs > Select "Turn Windows features on or off" 
 <p></p> - Check "Internet Information Services" box + expand it > Expand "World Wide Web Services" > Expand "Application Development Features > Then check the "CGI" box
</p>
<br />

<p>
<img src="https://i.imgur.com/HduU95q.jpeg"/>
</p>
<p> - Next, navigate to the "osTicket-Installation-Files" folder in File Explorer and double click + install PHP Manager 
</p>
<br />

<p>
<img src="https://i.imgur.com/sDEnu1w.jpeg"/>
</p>
<p>
- Inside the same folder, proceed to also install Rewrite Module
</p>
<br />

<p>
<img src="https://i.imgur.com/MmUaM8u.jpeg"/>
</p>
<p>
- Open a new File Explorer tab, and in the Windows(C:) drive inside "This PC" tab create a new folder called "PHP"
</p> - Once "PHP" folder is created > Proceed back to File Explorer tab with osTicket-Installation folder open 
</p> - Right click "php-7.3.8-nts.." > Extract All > Browse > Windows(C:) > PHP > Select Folder > Extract
</p>
<br />

<p>
<img src="https://i.imgur.com/6pC4iCj.jpeg"/> <img src="https://i.imgur.com/p0pHvgc.jpeg"/>
</p>
<p>
- Back inside osTicket-Installation folder, install VC_redist.x86 > Then install MYSQL-5.5.62 - Select typical installation when prompted 
 </p> - Before finishing installing MYSQL, check the launch box so MYSQL opens after installation 
</p>
<br />

<p>
<img src="https://i.imgur.com/gpHXyWF.jpeg"/>
</p>
<p>
- Once MYSQL open, select standard configuration > Then click next until you reach security options
</p> - Then enter the password "root" > then continue to execute
</p>
<br />

<p>
<img src="https://i.imgur.com/a1hUxvc.jpeg"/> <img src="https://i.imgur.com/5glTn44.jpeg"/> 
</p>
<p>
- Next step is to click the start menu > Type IIS + right click and run as admin
</p> - Then proceed to register PHP from within IIS: Select PHP manager > Click register new php version > Browse to PHP folder on C: drive 
</p> - Then double click php-cgi > Click OK
</p>
<br />

<p>
<img src="https://i.imgur.com/58gfLJX.jpeg"/>
</p>
<p>
- Reload IIS: Right click osTicket-vm in the Connections tab > Stop then Start again
</p>
<br />

<p>
<img src="https://i.imgur.com/tfMlHDC.png"/>
</p>
<p>
- Proceed back to the osTicket-Installation folder > Right click osTicket-v1.15.8 + Extract all > Open osTicket-v1.15.8
</p> - Open a new File Explorer tab > C: drive > inetpub > wwwroot
</p> - Drag "upload" folder inside osTicket-v1.15.8 into wwwroot folder > rename "upload" to "osTicket"
</p> - Reload IIS once again
</p>
<br />

<p>
<img src="https://i.imgur.com/k8vc81f.jpeg"/> <img src="https://i.imgur.com/8kEFSHV.jpeg"/>
</p>
<p>
- Drop down sites in IIS > Drop down Default Web Site > Click osTicket > On the far right under Manage Folder click Browse *:80 (http)
</p> - osTicket site should open 
</p>
<br />

<p>
<img src="https://i.imgur.com/Fx3FjdY.jpeg"/>
</p>
<p>
- Notice when you enter the osTicket site some extensions are not enabled lets fix that!
</p> - Open IIS > Sites > Default Web Site > PHP Manager > Enable/disable an extension 
</p> - Right click + enbale php_imap.dll, php_intl.dll, php_opcache.dll > Then refresh osTicket browser
</p>
<br />

<p>
<img src="https://i.imgur.com/QKM5ERU.jpeg"/>  <img src="https://i.imgur.com/PYqpYg3.jpeg"/>
</p>
<p>
- Next, rename ost-config.php inside File Explorer: Navigate to wwwroot > osTicket > inlcude folder 
</p> - Scroll down to ost-sampleconfig.php > Rename: ost-config.php  
</p>
<br />

<p>
<img src="https://i.imgur.com/VFqoNmK.jpeg"/>  <img src="https://i.imgur.com/OigMYLC.jpeg"/>
</p>
<p>
- Next step is to assign permissions inside ost-config.php
</p> - Right click ost-config.php > Properties > Security > disble inheritance > Select remove all inherited permissions
</p> - Then select add > Click select a principal at the top > Assign everyone permissions > click check names > OK
</p> - Check "Full Control" box > OK > Apply
</p>
<br />

<p>
<img src="https://i.imgur.com/L8LaxNC.png"/>
</p>
<p>
- Back inside the osTicket browser continue setting up
</p> - Since this is just a lab, names and emails don't have to be real  
</p>   
</p>
<br />

<p>
<img src="https://i.imgur.com/OHzqHM0.png"/>  <img src="https://i.imgur.com/ktx42b5.png"/>
</p>
<p>
- Before filling out Database Settings, HeidiSQL needs to be installed
</p> - Proceed back to osTicket-Installation-Files Folder on the Desktop > Double click HeidiSQL > I Accept > Next 4x > Install
</p> - Check "Launch HeidiSQL" > Finish > Skip > Click New on bottom left > enter "root" password that was created previously > Click Open
</p> - Right click "Unnamed" > Create New > Database > Name: osTicket > OK
</p>
<br />

<p>
<img src="https://i.imgur.com/w1Dku07.png"/>
</p>
<p>
- Back to the osTicket website to fill out Database Settings
</p> - MySQL Database: osTicket | MySQL Username: root | MySQL Password: root 
</p> - Click Install Now > Should see a Congratulations message once osTicket has been successfully installed
</p>
<br />
