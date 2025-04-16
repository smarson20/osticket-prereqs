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
Follow the default prompts for both executables.
</p>

</br>


<br>

## V. Setup PHP

- Navigate to the C: Drive and create a new directory. Title it `C:\PHP`.

![Alt text](https://imgur.com/9poP1Yr.png)

![Alt text](https://imgur.com/eCzLpuJ.png)


- Unzip `PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip)` into the `C:\PHP` folder.

![Alt text](https://imgur.com/7SCofDY.png)

- Run the executable VC_redist.x86.exe. Follow through with the installation.


![Alt text](https://imgur.com/3oueiag.png)

</p>


</br>


<br>


## VI. Install MySQL


From the `os-Ticket-Installation-Files` folder, install **MySQL 5.5.62** (`mysql-5.5.62-win32.msi`):

![Alt text](https://imgur.com/uiPtHL3.png)

- Select **Typical Setup**

![Alt text](https://imgur.com/kPMCGpq.png)

- After installation, launch the **MySQL Configuration Wizard**

![Alt text](https://imgur.com/lMjvrke.png)

  - Choose **Standard Configuration**

![Alt text](https://imgur.com/17oQ8ZK.png)

  - Set a **username** and a **reliable password**


![Alt text](https://imgur.com/xvfgNSc.png)



</br>

<br>

  ## VII. Configure Internet Informational Services (IIS)


- Open IIS as an administrator.

![Alt text](https://imgur.com/BbjzCVT.png)


- Register PHP:
  - Go to **PHP Manager** -> Register new PHP version -> `C:\PHP\php-cgi.exe`.

![Alt text](https://imgur.com/WOgkPDO.png)


![Alt text](https://imgur.com/1pxc65N.png)


![Alt text](https://imgur.com/y8IZaim.png)

- Reload IIS. Under the `Manage Server` heading in the `Actions` tabs, click the `Restart` button to reload the server.


![Alt text](https://imgur.com/SmtYaEw.png)


<br>

  ## VIII. Install osTicket


- From the `osTicket-Installation-Files` folder:
    - Unzip `osTicket-v1.15.8.zip`.


![Alt text](https://imgur.com/gJKlU8Y.png)


  - Locate the `upload` folder and move it into `C:\inetpub\wwwroot`.

![Alt text](https://imgur.com/ZYYinxo.png)

![Alt text](https://imgur.com/7RVXfzR.png)


  - Rename the `upload` folder to `osTicket`.


![Alt text](https://imgur.com/YrCI7Q5.png)
    
- Once again, restart the IIS server.



## IX. Configure osTicket

- Open `Internet Informational Services`:
    - Navigate to the `Connections` tab on the left, and click on the `osTicket` folder; `Sites` -> `Default Web Site` -> `osTicket`.

![Alt text](https://imgur.com/8XVX5yY.png)

  - On the right, under the  click **Browse :80*.

![Alt text](https://imgur.com/jO9dltT.png)




*Note that certain extensions have not been enabled.*

![Alt text](https://imgur.com/cmt7v3f.png)


 Return to `Internet Informational Services`:
    - Navigate to `Sites` -> `Default Web Site` -> `osTicket`
    - Double-click `PHP Manager` -> Click `Enable or disable an extension`.

![Alt text](https://imgur.com/fk20IIT.png)
    
  - Enable the following extensions:
        - `php_imap.dll`
        - `php_intl.dll`
        - `php_opache.dll`

![Alt text](https://imgur.com/FCTZjPt.png)


Refresh the osTicket site in your browser, observe the changes made.

![Alt text](https://imgur.com/qHn2wFq.png)



## X. Update Configuartion Files

Rename `ost-config.php`:
  -From: `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`
  -To: `C:\inetpub\wwwroot\osTicket\include\ost-config.php`

![Alt text](https://imgur.com/yBUPxD4.png)

![Alt text](https://imgur.com/fuELF1g.png)

Assign Permissions:

  - Right click `ost-config.php` and select `Properties`.

![Alt text](https://imgur.com/qp8bQGW.png)

  - Under the `Security` tab, select the `Advanced` button for access to advanced settings.

![Alt text](https://imgur.com/8L0jpoa.png)


  - Disable inheritance -> Remove all inherited permissions

![Alt text](https://imgur.com/lLN2uNn.png)


  - Click the `Add` button. Follow up by selecting `Select a Principal`.

![Alt text](https://imgur.com/xOTLHN2.png)




  - For the sake of this example, we will be adding `Everyone` as a Group. After typing `everyone`, click the `Check Names` button.

![Alt text](https://imgur.com/lgILCCf.png)

  - Hit the `Apply` button, then `OK` to continue.



## XI. Complete osTicket Setup

In the browser, select the `Continue` button to proceed with the osTicket setup:
  - Set **Helpdesk Name**.

![Alt text](https://imgur.com/xVidLod.png)
  
  - Set **Default E-mail** (this will be the handle that receives e-mails from clientele).

![Alt text](https://imgur.com/qeN2MCB.png)


  - Proceed by inputting credentials for the Admin User; First Name/Last Name, an e-mail address as well as a reliable username and password.

## XII. Install HeidiSQL and Configure Database

From the `osTicket-Installation-Files` folder, install HeidiSQL.

![Alt text](https://imgur.com/8SOzt8H.png)

Open HeidiSQL and:
  - Create a new session:
  
![Alt text](https://imgur.com/WMYZ2zu.png)

  Head to the `Settings` tab. When prompted for a Username and Password, be sure to input the credentials you used when setting up the MySQL Server. Aftewards, click the `Open` button.

![Alt text](https://imgur.com/vLwM5Jq.png)
  
  - Connect to the new session.

![Alt text](https://imgur.com/FaoF5zd.png)

  - Create a new database named **osTicket** (case sensitive).
  
![Alt text](https://imgur.com/SoqdhEI.png)



## XIII. Finalize osTicket Installation

In the browser, complete the setup by filling in the following:
  - MySQL Database: osTicket
  - Your Username and Password for MySQL

**Install**


![Alt text](https://imgur.com/X89dZ5s.png)



## XIV. Verify Installation 


![Alt text](https://imgur.com/yF9EpW7.png)


- Browse the `osTicket` database in Heidi. Right-click and `Refresh` the database:

![Alt text](https://imgur.com/xeBZ72F.png)

You will now see the database populated with a number of tables.

![Alt text](https://imgur.com/WEixvLU.png)

Access your help desk login page: `http://localhost/osTicket/scp/login.php`.

![Alt text](https://imgur.com/avDdZfO.png)

Add in your Admin credentials used during setup. And you're in!


</p>

<h2> Conclusion </h2>

<p>
  Congratulations. You have now installed and configured osTicket on your WindowsOS! Your help desk system is ready to use!
</p>
