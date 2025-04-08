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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- Windows 10 (64-bit preferred), whether native or launched through a Microsoft Azure-based Virtual Machine
- Web Server Stack. An individual installation of an HTTP Server, a MySQL Server, and PHP 8.0-8.1
- Enabling of the necessary PHP extensions
- osTicket Download + Database Setup
- Enabling File & Folder Permissions

<h2>Installation Steps</h2>


<h2>Prepping the Stage</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
If using native Win10 OS, then feel free to skip to the next part. For the sake of this guide, we will prepare a Virtual Machine using Microsoft Azure. First and foremost, we will create a VM. You will be prompted to title it, and you may choose whatever name you please. For the sake of this guide we will call our Virtual Machine "osTicket".
<ul>
If not done already, please go ahead and create a Resource Group to nest the VM inside of.
</ul>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Select your region of choice. For ideal usability, you should select a region that is closest to you. In this instance, we will select East-US 2. Follow up by choosing Windows 10 Pro, version 22H2 as the Image (Operating System) for our use.
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Select your preferred CPU Size. For ease-of-use, select a size with no fewer than 2 VCPUs. Enter adminstrative credentials (i.e, a user handle and a reliable password), and do not forget to select the licensing box.

Once done, you may click the 'Review + Create' button and proceed. No changes are necessary for the Management, Disks, or Networking sections in this VM creation portal.

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
