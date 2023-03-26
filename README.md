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

- Setup Azure Tenant
- Have an active subsctiption
- Created an Azure Resource Group and Virtual Machine using Windows 10

<h2>Installation Steps</h2>

<p>1. Log in to your Azure Virtual Machine</p>
<br />

<p>
2. Enable IIS with CGI.
</p>
<p>
<img src="https://i.imgur.com/ql6QlGq.png" height="80%" width="80%" alt="enable iis with cgi"/>
</p>
<br />

<p>
3. Download and install PHP manager and Rewrite Module for IIS.
</p>
<p>
<img src="https://i.imgur.com/okhEXOb.png" height="80%" width="40%" alt="install php manager"/>
<img src="https://i.imgur.com/2L1iVLd.png" height="80%" width="40%" alt="install rewrite module"/>
</p>
<br />

<p>
4. Create a folder titled PHP in the C drive.
</p>
<p>
<img src="https://i.imgur.com/CZUgDaq.png" height="80%" width="80%" alt="create php folder in c drive"/>
</p>
<br />

<p>
5. Download PHP 7.3.8 and extract all files to newly created PHP folder
</p>
<p>
<img src="https://i.imgur.com/xSMHDyV.png" height="80%" width="80%" alt="extract files to PHP folder"/>
</p>
<br />

<p>
6. Download and install VC_redist.x86.exe
</p>
<p>
<img src="https://i.imgur.com/28qmME6.png" height="80%" width="80%" alt="download and install vc_redist.x86"/>
</p>
<br />

<p>
7. Download and install MySQL 5.5.62. Typical install. 
</p>
<p>
<img src="https://i.imgur.com/ou1IGxT.png" height="80%" width="80%" alt="download and install mysql"/>
<img src="https://i.imgur.com/6UNWi88.png" height="80%" width="80%" alt="download and install mysql"/>
</p>
<br />

<p>
8. Open IIS as admin
</p>
<p>
<img src="https://i.imgur.com/23ONuVT.png" height="80%" width="80%" alt="open iis as admin"/>
<img src="https://i.imgur.com/9cVQvfI.png" height="80%" width="80%" alt="iis open"/>
</p>
<br />

<p>
9. Register PHP in IIS with PHP Manager and restart server
</p>
<p>
<img src="https://i.imgur.com/1oKsn0I.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/d6ih4gZ.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
10. Download OSTicket
</p>
<p>
<img src="https://i.imgur.com/q1VepgN.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
11. Extract and copy “upload” folder to C:\inetpub\wwwroot
</p>
<br />
<p>
12. Rename “upload” to “osTicket” and restart IIS server
</p>
<p>
<img src="https://i.imgur.com/s6QOKmV.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
13. In IIS go to "Sites" -> "Default Web Site" -> "osTicket", then on the right, click “Browse *:80”
</p>
<p>
<img src="https://i.imgur.com/Mn5o2I9.png" height="80%" width="80%" alt=""/>
</p>
<p>
<img src="https://i.imgur.com/zBNdqDh.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
14. In IIS, "Sites" -> "Default Web Site" -> "osTicket" -> "PHP Manager" -> "Enable or disable an extension"
  <br />
  Enable the following: <br />
    - php_imap.dll <br />
    - php_intl.dll <br />
    - php.opcache.dll <br />
  Restart server.
</p>
<p>
<img src="https://i.imgur.com/SGc5EGi.png" height="80%" width="80%" alt=""/>
</p>
<p>
<img src="https://i.imgur.com/vMRx9Xv.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
15. Go to "C:\inetpub\wwwroot\osTicket\include\" and rename "ost-sampleconfig.php" to "ost-config.php"
</p>
<p>
<img src="https://i.imgur.com/jsBAf5R.png" height="80%" width="80%" alt=""/>
<img src="https://i.imgur.com/HIWhuT9.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
16. Right click -> Properties -> Security -> Disable Inheritance -> Remove all -> New permissions -> Everyone -> All
</p>
<p>
<img src="blob:https://imgur.com/7ca02a25-b826-4b78-8d9d-044f2f9ddcdf" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
17. Continue setup of osTicket in the browser and stop when you get to Databse Settings 
</p>
<p>
<img src="https://i.imgur.com/NmuiuMv.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
18. Download and install HeidiSQL
</p>
<p>
<img src="https://i.imgur.com/OyFZ5yP.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
19. Create a new session and connect
</p>
<p>
<img src="https://i.imgur.com/XXlig72.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
20. Create a database called "osTicket"
</p>
<p>
<img src="https://i.imgur.com/6ZeqwJX.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
21. Delete "setup" folder in "C:\inetpub\wwwroot\osTicket" and set Permissions to “Read” only for "ost-config.php" file in "C:\inetpub\wwwroot\osTicket\include"
</p>
<p>
<img src="https://i.imgur.com/opE84D4.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
22. Browse to your help desk login page: http://localhost/osTicket/scp/login.php  <br/> End Users osTicket URL: http://localhost/osTicket/
</p>
<p>
<img src="https://i.imgur.com/vf3SoDe.png" height="80%" width="80%" alt=""/>
</p>
<br />

<p>
22. Log in to osTicket using username and password created during setup
</p>
<p>
<img src="https://i.imgur.com/Z2bhhxe.png" height="80%" width="80%" alt=""/>
</p>
<br />
