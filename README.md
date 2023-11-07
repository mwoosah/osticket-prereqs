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

- Files of Prerequisites https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6


<h2>Login URL Links</h2>

- Help desk login page: http://localhost/osTicket/scp/login.php 

- End Users osTicket URL: http://localhost/osTicket/



  STEP 1:
  *Install / Enable IIS in Windows WITH CGI and Common HTTP Features*
  1.  Click on the windows start menu logo
2.  Type Control Panel in the search bar located at the top of the window
3. Click on the control panel Icon or App
4. Click on Programs that is highlighted in green
5. Click on turn windows features on or off that is highlighted in blue next to a shield icon
6. Once that window pops up, Scroll or look until you see Internet Information Services
7. Check the Internet Information Services box (IIS) 
8. Click on the + Symbol next to where it says Internet Information Services
9. On that dropdown you want to look for where it says World Wide Web Services
10. Click the + Symbol next to World Wide Web Services
11. On that dropdown you want to look for where it says Application Developmet Features
12. Click the + Symbol next to Application Development Features
13. Check the CGI Box
14. Press the - Symbol next to Application Development Features
15. Click the + Symbol Next to Common HTTP Features
16. Check off all the boxes inside of it
17. Click ok and then close everything
18. Open up a web browser and type 127.0.0.1 and press enter to check



  STEP 2:
  *Download and installing PHP Manager for IIS and Rewrite Module*
  1. Download Link (PHP Manager for IIS) : https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link
  2. Download Link (Rewrite Module): https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link


  STEP 3:
  *Create the directory C:\PHP and install content into it*
  1. Download and install VC_redist.x86.exe. - https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link
2. Click on the folder Icon on windows
3. Click on this PC
4. Click on Local (C:)
5. Right Click an empty space and create a new folder called ‘PHP’
6. Download PHP 7.3.8 and extract the content into that new folder called ‘PHP’ - https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link





  STEP 4:
  *Downloading and installing MySQl server and setting up a Username and password*
  1. Download and install MySQL 5.5.62
2. MySQL Server Instance Configuration: Click on Standard Configuration
3. Click Next
4. Set New Root Username and Password
5. Username: root (example)
6. Password: Password1 (example)
7. Press Execute and then press finished when it is done






  STEP 5:
*Open IIS as an Admin > Register PHP from within IIS*
1. Click on the windows icon and search IIS
2. Right Click on the icon and run as ‘Admin’
3. Double Click on the PHP Manager Icon
4. Click on Register New PHP Version
5. Click on the 3 Dots Next to it
6. Browse to the PHP folder and inside it click on the php-cgi.exe
7. Reload the IIS Server





  STEP 6:
  *Install osTicket > extracting contents into it*
  1. Download osTicket https://drive.google.com/file/d/1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ/view?usp=drive_link
2. Open the osTicket Zip Folder you should see an folder called upload
3. Keep that window open
4. Go to your (C:) drive > Click on the ‘inetpub’ folder
5. Click on wwwroot > Then drag and drop the ‘upload folder into the wwwroot folder.
6. Rename the upload folder to ‘osTicket'






  STEP 7:
  *Going to the osTicket instalation website and configuring a few settings inside of the IIS Server*
  1. Reload the IIS Server (Inside the IIS App)
2. vm-osticket > Application Pools > Sites > Default website > 'osTicket'
3. On the right click on Browse start 80
4. Go back to IIS then click on ‘osTicket’
5. Double click Php manager icon
6. Click on Enable or Disable an Extension
- Enable: php_imap.dll
- Enable: php_intl.dll
- Enable: php_opcache.dll
8. Refresh the browser to see the changes







  STEP 8:
  *renaming ost-sampleconfig.php inside the osTicket Folder*
  1. Browse to the osTicket folder (This PC > Windows (C:) >  inetpub > wwwroot > osTicket)                                 
2. Click on the 'Include' folder
3. Scroll down and rename the ost-sampleconfig.php simply to ost-config.php


  

  STEP 9:
*Assign Permissions: ost-config.php*
1. Right click  on ost-config.php
2. Click properties
3. Click Security
4. Click Advanced
5. Click ‘Disabled Inheritance at the bottom
6. Click Remote all inherited permissions from this object
7. Click Add
8. Click select a principal 
9. Type ‘everyone’ at the bottom and press check names
10. In the basic permissions check all of the boxes and then click ok
11. Click apply ok > ok


  

  STEP 10:
*Continue Setting up osTicket in the browser (click Continue)*

         *System Settings*
- Helpdesk Name: John Help Desk (example)
- Default Email: John@helper.com (example)
- Primary Language: English (set to your language)



         *Admin User*
- First name: John (example)
- Last name:  Doe (example)
- Email Address: John@gmail.com (example)
- Username: John (example)
- Password: JohnDoe123 (example)
 


       *DATABASE SETTINGS*
- MySQL Database: osTicket (required)
- MySQL Username: root (example)
- MySQL Password: Password1 (example)



  STEP 11:
*Download and install HeidiSQL create a new database*
1. Download and install HeidiSQL: https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit
2. Open Heidi SQL
3. Click New
4. Set User: root
5. Set Password: Password1
6. Click open
7. Right Click Unnamed on the top left
8. Create new database
9. Rename it ‘osTicket’ then click ok
10. Go back to the osTicket browser and set the rest of the info in and press install




  STEP 12:
  *Clean up proccess*
  1. Delete: C:\inetpub\wwwroot\osTicket\setup
2. Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php
- Note: 'Include' folder inside of osTicket to delete it
