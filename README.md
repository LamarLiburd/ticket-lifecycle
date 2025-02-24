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
- osTicket v1.18.2

<h2>Installation Steps</h2>

1.)First, go to [https://portal.azure.com/](https://portal.azure.com/) to create a virtual machine. Set it up with **Windows 10 Pro, version 22H2**. Make sure the virtual machine has at least **2 vCPUs** and **16 GB of memory**.

2.) Once your virtual machine is created, connect to it using the **public IP address** assigned to the VM. Use the **Remote Desktop Connection** app to establish the connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/MAhXK2e.png" alt="Disk Sanitization Steps" style="max-width: 80%; height: auto;">

</p>
<p>
<p>
<img src="https://i.imgur.com/Zf2jw07.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
3.) Once connected to your virtual machine you will want to go to your control panel. From the control panel open up programs. Select and turn Windows features on and off.

<p>
<img src="https://i.imgur.com/fGXMpx4.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
<p>
<img src="https://i.imgur.com/LBGkAw6.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
4.) You will want to install/enable IIS in Windows with CGI and Common HTTP Features
- World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Common HTTP Features
<p>
<img src="https://i.imgur.com/LQjw9le.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
<p>
<img src="https://i.imgur.com/pbPeHb1.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
Ensure that all **Common HTTP Features** are selected.
To make sure the IIS is installed/enabled go to a browser of your choice and search for 127.0.0.1
It should look something like this.
<p>
<img src="https://i.imgur.com/eICujoq.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
5.)With IIS enabled, download and install **PHP Manager for IIS** (*PHPManagerForIIS_V1.5.0.msi*) from the installation files, then follow the installation wizard to complete the setup.
6.) Next from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)
7.) Create a folder in the C drive called PHP.
8.) From the installation files, download **PHP 7.3.8** (*php-7.3.8-nts-Win32-VC15-x86.zip*) and extract its contents into **C:\PHP**.  

If a warning appears, select **"Keep"** to proceed.
<p>
<img src="https://i.imgur.com/xZv1Yhw.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
<p>
<img src="https://i.imgur.com/YwBhqo0.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>

9.) After downloading and extracting the ZIP file into the **PHP** folder on the **C:** drive, download and install **VC_redist.x86.exe** from the installation files. Follow the setup wizard to complete the installation.
10.) Download and install MySQL 5.5.62 (MySQL-5.5.62-win32.msi)
Run the setup wizard:
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->

Make the new root password: Password1
<p>
<img src="https://i.imgur.com/KxcUy7C.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
Execute the process on the following page.
<p>
<img src="https://i.imgur.com/i7sn6hT.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
11.) Now that we have the files downloaded and installed we will want to search for IIS in the Windows search bar. Open IIS as an administrator.
The program should look like this.
<p>
<img src="https://i.imgur.com/rgdZwmM.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
12.) We will now want to register PHP from within IIS.
Click on PHP Manager
<p>
<img src="https://i.imgur.com/vvTLNBH.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
Register for the new PHP version.
<p>
<img src="https://imgur.com/qdbn5zQ.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Provide the path to the **PHP executable file** (**php-cgi.exe**).  

Navigate to **C:\PHP** and select the **php-cgi.exe** file.
<p>
<img src="https://imgur.com/oJZ0gp9.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Restart the IIS server.
<p>
<img src="https://imgur.com/CJ3RUbG.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
13.) Install osTicket v1.18.2
-Download osTicket from the Installation Files Folder
-Extract and copy the "upload" folder to c:\inetpub\wwwroot
-Within c:\inetpub\root, Rename "upload" to "osTicket"
Reload IIS again.
14.) On IIS go to sites -> Default -> osTicket
-On the right, click “Browse *:80”
<p>
<img src="https://imgur.com/Yw55d5b.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Some extensions are not enabled on the osTicket browser.
<p>
<img src="https://imgur.com/eJIsGTn.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
To enable the extensions:  

1. Open **IIS** and navigate to **Sites → Default → osTicket**.  
2. Double-click **PHP Manager**.  
3. Select **"Enable or disable an extension."**
<img src="https://imgur.com/vvTLNBH.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
<p>
<img src="https://imgur.com/uigyKjb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
We will want to enable three extensions from here.
1.) php_imap.dll
2.) php_intl.dll
3.) php_opcache.dll
<p>
<img src="https://imgur.com/cOem7Nb.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
15. Once those extensions are enabled in IIS, the next step is to rename a file in the **osTicket** folder.  

1. Open **File Explorer** and navigate to:  
   **C:\inetpub\wwwroot\osTicket\include\ost-sample config.php**  
2. Rename **ost-sampleconfig.php** to **ost-config.php**.  
3. Right-click the renamed file and select **Properties**.  
4. Go to the **Security** tab, click **Advanced**, and disable inheritance.  
5. Choose to **remove all inherited permissions** from this object.  
6. Click **Add** to set new permissions.
<p>
<img src="https://imgur.com/VPZvOdo.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Select a principal
<p>
<img src="https://imgur.com/PoGk34d.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Type "Everyone" in the box.
<p>
<img src="https://imgur.com/F4H3ppM.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Make sure "Full Control" and all other checkboxes are selected.
<p>
<img src="https://imgur.com/rbbGqwB.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click Apply and Ok.
<p>
<img src="https://i.imgur.com/saRO3y5.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
Once complete, continue setting up **osTicket** in the browser. Click **Continue** and fill out the required fields, except for **Database Settings**—we’ll handle that later.
Next, download and install **HeidiSQL** from the installation files.
<p>
<img src="https://imgur.com/i7a4gWC.png" height="40%" width="40%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the program is open, we will create a new session.
<p>
<img src="https://i.imgur.com/g5M1i61.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

<p>
Be sure the username is set to **root** and the password to **Password1**.
<p>
<img src="https://i.imgur.com/LEAZNOc.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
After connecting to the session, return to the browser to continue the setup. In **Database Settings**, set the username to **"root"** and the password to **"Password1."**  

Next, create a new database in **HeidiSQL**:  
1. In **HeidiSQL**, right-click on **"Unnamed"** in the left panel.  
2. Select **"Create new" → "Database."**  
3. Name the database **osTicket** and complete the setup.  

After creating the database, go back to the **osTicket** setup page in the browser and enter **osTicket** in the **MySQL Database** field.
<img src="https://i.imgur.com/0rG1AJm.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
The final step is cleanup. Delete the **setup** folder from your system:  

- **Delete:** *C:\inetpub\wwwroot\osTicket\setup*  
  *(Only delete the setup folder—do not remove anything else.)*  

Then, set the **ost-config.php** file permissions back to **"Read" only**.
<img src="https://i.imgur.com/wFr0pkK.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
<p>
<img src="https://i.imgur.com/jsJOPyn.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
The final step is to log in to **osTicket** through the browser.
<p>
<img src="https://i.imgur.com/uHVdDsx.png" alt="Disk Sanitization Steps" style="max-width: 40%; height: auto;">

</p>
<p>
Congrats! You have now successfully installed and set up osTicket!


