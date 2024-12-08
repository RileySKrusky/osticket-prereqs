<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- oSTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Installation Steps</h2>
<h3>1) Creating a Virtual Machine</h3>
<p>
Start by searching and selecting the virtual machine service in the search bar (Make sure you select "Virtual Machine", not "Virtual Networks"). 
</p>

<p>
<img src="https://i.imgur.com/E8texzH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<br />
<h3>2)Setting up Resource Group</h3>
<p>
 After clicking on the "virtual machine name", you can name it anything you like; for this tutorial, we’ll use "osticket-vm." Select "create new resource group" to place the virtual machine into it, and name the resource group "os-ticket." Choose your region based on your location (e.g., "Central Canada" if you're in Canada).

Scroll down to find the "image" option and select "Windows 10 Pro, Version 22H2, x64 Gen2." Ensure the virtual machine has at least 2 vCPUs and 16 GB of memory, which you can set in the size option on the same page.

You don’t need to any default settings on the following pages, but make sure the licensing box is checked on the first page. Once done, proceed to review and create the virtual machine. The system will automatically create a virtual network, so you don’t need to configure that..

<p>
<img src="https://i.imgur.com/G2mmFrE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>3)Connecting to Remote Desktop</h3>
  <p> After all these steps are excecuted, you can then move on to connecting to your virtual machine using "Remote Desktop Connecion". Make sure to grab your "Public IP Adress". (You will find this by clicking on your virtual machine you just created. It should be near the top right of the screen). Make sure your virtual machines Public IP Adress is pasted properly in the Remote Desktop Connection.</p>
</p>
<p>
<img src="https://i.imgur.com/XhlWo4x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://i.imgur.com/kgPFpyr.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<h3>4)Downloading OsTicket</h3>
<p>
 After you have logged into your "Remote Desktop", you can then procceed to download the "OsTicket" File provided here https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD. simply copy this link and paste it into a browser on your Virtual machine. Download and unzip this folder to your desktop.
  <p>
<img src="https://i.imgur.com/O6NDJSp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>5)Installing IIS</h3>
<p>
In your virtual machine, go to the bottom right in your windows search bar and type in "Control Panel". With this window open, go to "Uninstall Programs" Under "Programs".  
  <img src="https://i.imgur.com/6h7KEce.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In the "Programs and Features" window on the left, select the "Turn Windows Features on or off" option.
  <img src="https://i.imgur.com/JVFGkJO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this window, click "Internet Information Services" -> "World Wide Web Services" -> "Application Development Features" -> Make sure "CGI" has a checkmark to the left of it. procceed to click ok at the bottom right and wait till the changes are installed.
</p>
<img src="https://i.imgur.com/BiHgIUb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<h3>6)Installing Applications</h3>
<p>
After you have installed "IIS", you then open your "osticket" folder and procceed to install php manager. All the settings through this installation are fine to leave as is, so continue through the php manager installation portal.
  <img src="https://i.imgur.com/fddo2dU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>The same goes for the "rewrite_amd64" file in the osticket folder. simply procceed through that installation portal as well.
  <img src="https://i.imgur.com/ymvr1n0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>After "IIS", "PHP manager" and "rewrite_amd64" are installed, go into your file explorer in your windows shortcut bar on the bottom and in your "Windows (C:)" drive under "This PC" create a "PHP" folder. Once Created, go into your "osticket" folder and extract the "php-7.3.8-nts-Win32-VC15-x86" folder to your "PHP" folder you just created in your "C" drive
<img src="https://i.imgur.com/jpz5HFD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/></p>
<p>Procceed to instal these two files as well in the "osticket" folder:"mysql-5.5.62-win32" and "VC_redist.x86". For the "mysql-5.5.62-win32" folder, you will get to a screen that says "Choose Setup Type" select "Typical" and procceed with the rest of the installtion.</p>
<img src="https://i.imgur.com/c7Me047.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/jaBVJRT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<h3>7)Launching MySQL</h3>
<p>After you have installed "mysql-5.5.62-win32", at the last slide of the installation proccess it will tell you that "My SQL" will laucnh after installation. make sure this is checked. Go through the installation proccess until you get to this screen. choose "Standard Configuration" and procceed.
  
<img src="https://i.imgur.com/OPsmJeU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/></p>

<p> Continue untill you get to a slide that gives you two options, "Modify Security Settings" and "Create an Anonymous Account". Make sure to select "Modify Security Settings" and create a password (make sure to put the password somewhere safe because we will be coming back and using it in this tutorial). 
</p>
 <img src="https://i.imgur.com/JLWIg3w.png" height="60%" width="40%" alt="Disk Sanitization Steps"/>
<br />
<p>After you have created a password, click "Next", "Execute" and "Finish"</p>
<h3>8)Open IIS as an Admin</h3>
<p>Go to your search bar on the bottom right of your windows desktop and search for "Internet Information Services (IIS) Manager". Right-click and select "run as administrator"</p>

<img src="https://i.imgur.com/8B9O9hP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
