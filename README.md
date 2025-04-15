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

<br>

## I. Staging

<p>

![Alt text](https://imgur.com/HxNSrHT.png)


</p>
<p>
If using native Win10 OS, then feel free to skip to the next part. For the sake of this guide, we will prepare a Virtual Machine using Microsoft Azure. Navigate to the Virtual Machine portal through Azura and click the 'Create' button (denoted by a + symbol). Once inside, you will be prompted to title your Virtual Machine, and you may choose whatever name you please. For the sake of this guide we will call our Virtual Machine "osTicket".
<ul>
If not done already, please go ahead and create a Resource Group to nest the VM inside of.
</ul>
</p>


![Alt text](https://imgur.com/5PL53js.png)


<p>
Select your region of choice. For ideal usability, you should select a region that is closest to you. In this instance, we will select East-US 2. Follow up by choosing Windows 10 Pro, version 22H2 as the Image (Operating System) for our use.
</p>


![Alt text](https://imgur.com/JaPhl0R.png)

<p>
Select your preferred CPU Size. For ease-of-use, select a size with no fewer than 2 VCPUs. Enter adminstrative credentials (i.e, a user handle and a reliable password), and do not forget to select the licensing checkbox at the bottom of the page.

Once done, you may click the 'Review + Create' button and proceed. No changes are necessary for the Management, Disks, or Networking sections in this VM creation portal. Azure will take several moments as it finishes generations of your Virtual Machine. Once it does, make sure to head to the Virtual Machine portal and take note of the Public IP address assigned to your VM.


![Alt text](https://imgur.com/csfXr13.png)

<p>
Locate the 'Remote Desktop Connection' program, either through a simple search on the taskbar. Copy the Public IP address assigned to your Virtual Machine and paste it in the 'Computer' field. Afterward, feel free to click on the 'Connect' button.

You will be prompted to fill in the user name and password associated with the VM. This is the administrative credentials you had used in the creation of the Virtual Machine, earlier. Enter your credentials and proceed.

  
</p>

</br>

<br>


## II. Download and Prepare Installation Files


![Alt text](https://imgur.com/A9lGPPU.png)



 Download the <a href="https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD" download>
  `Download the osTicket Installation Files (.zip)`
</a> and install it to your Desktop.



 ## III. Enable Internet Information Services and Its Required Features

<p>
  Open the Control Panel and navigate to the Programs and Features menu (e.g, Control Panel -> Programs). There you will be presented with a number of programs installed on your PC. To your left, you will be presented with the feature titled 'Turn Windows features on or off'. Click it. 
</p>


![Alt text](https://imgur.com/ScfhwIB.png)

![Alt text](https://imgur.com/4vSSJcd.png)

<p>
You will be presented with a menu of a large directory. Scroll to look for 'Internet Information Services'. If not done so already, please enable it. Open its directory and open the 'World Wide Web Services'. From there, select the 'CGI' feature listed under 'Application Development Features' to enable it as well.
</p>

![Alt text](https://imgur.com/RstYsk8.png)

</br>

![Alt text](https://imgur.com/adlfoGl.png)

<p>
You can confirm the installation of the web servers was a success by typing '127.0.0.1' in a browser and receiving the IIS splashpage in return. 
</p>

<br>

  ## IV. Install Required Components


From the `osTicket-Installation-Files folder`:

- Install the PHP Manager for IIS: `PHPManagerForIIS_V1.5.0.msi`.
- Install the Rewrite Module: `rewrite_amd64_en-US.msi`.

</p>

![Alt text](https://imgur.com/Oj81DcW.png)

![Alt text](https://imgur.com/o7kMVKL.png)


<p>
Follow the default installation for both executables.
</p>

</br>


<br>

## V. Setup PHP

- Navigate to the C: Drive and create a new directory. Title it `C:\PHP`.

![Alt text](https://imgur.com/9poP1Yr.png)

![Alt text](https://imgur.com/eCzLpuJ.png)


- Unzip `PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)` into the `C:\PHP` folder.

![Alt text](https://imgur.com/7SCofDY.png)

- Run the executable VC_redist.x86.exe. Follow through with the default prompts for the installer.

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


</br>


<br>


## VI. Install MySQL

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the os-Ticket-Installation-Files folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi).
</p>

From the `os-Ticket-Installation-Files` folder, install **MySQL 5.5.62** (`mysql-5.5.62-win32.msi`):

- Select **Typical Setup**
- After installation, launch the **MySQL Configuration Wizard**
  - Choose **Standard Configuration**
  - Set a **username** and a **reliable password**

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>



</br>

<br>

  ## VII. Configure Internet Informational Services (IIS)


- Open IIS as an administrator.
- Register PHP:
  - Go to **PHP Manager** -> Register PHP Path -> `C:\PHP\php-cgi.exe`.
- Reload IIS. At this point you will want to restart your computer. For Virtual Machine users, you may close the VM or sign out. Once in the Virtual Machines portal, click the 'Stop' button and then restart it by clicking the 'Start' button. This will effectively reset the VM.


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

</br>



<br>

  ## VIII. Install osTicket


- From the `osTicket-Installation-Files` folder:
    - Unzip `osTicket-v1.15.8.zip`.
    - Copy the `upload` folder into `C:\inetpub\wwwroot`.
    - Rename the `upload` folder to `osTicket`.
- Once again, restart your computer.


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## IX. Configure osTicket

- Open `Internet Informational Services`:
    - Navigate to **Sites** -> **Default** -> **osTickets**.
    - On the right, click **Browse :80*.


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

*Note that certain extensions have not been enabled.* Return to `Internet Informational Services`:
    - Navigate to **Sites** -> **Default** -> **osTicket**
    - Double-click **PHP Manager** -> Click `Enable or disable an extension`.
    - Enable the following extensions:
        - `php_imap.dll`
        - `php_intl.dll`
        - `php_opache.dll`


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## X. Update Configuartion Files

Rename `ost-config.php`:
  -From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
  -To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`

Assign Permissions:
  - Disable inheritance -> Remove all permissions
  - Add new permissions -> **Everyone** -> **Full control**



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## XI. Complete osTicket Setup

In the browser, continue the osTicket setup:
  - Set **Helpdesk Name**.
  - Set **Default E-mail** (this will be the handle that receives e-mails from clientele).



<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## XII. Install HeidiSQL and Configure Database

From the `osTicket-Installation-Files` folder, install HeidiSQL.
Open HeidiSQL and:
  - Create a new session: **Username:** root / **Password:** root.
  - Connection to the new session.
  - Create a new database named `osTicket`.
  

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## XIII. Finalize osTicket Installation

In the browser, complete the setup by filling in the following:
  - MySQL Database: osTicket
  - MySQL Username: root
  - MySQL Password: root

**Install**

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


## XIV. Verify Installation 


Access your help desk login page: `http://localhost/osTicket/scp/login.php`.


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<h2> Conclusion </h2>

<p>
  Congratulations. You have now installed and configured osTicket on your WindowsOS! Your help desk system is ready to use!
</p>
