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

- Create a VM in Azure
- Install and enable IIS with CGI and Common HTTP Features and IIS Management Console
- Install PHP Manager for IIS and the Rewrite Module
- Create a C:\PHP directory
- Download PHP and unzip it to C:\PHP
- Install VC_Redist (software package that provides necessary components for C++ developed applications)
- Download and install MySQL
- Register PHP from within IIS as an Admin
- Download and install osTicket
- Assign permissions
- Download and Install HeidiSQL
- Finish setting up osTicket in the browser


<h2>Installation Steps</h2>

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/367ade6d-2ec0-424f-bff8-70aae112f41e)


Create a Virtual Machine in Microsoft Azure running Windows 10. In this example I used a 2vCPUs machine with 16GiB RAM
</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/40516453-c25c-4a68-9dc1-75bd9a602340)

World Wide Web Services -> Application Development Features ->
[X] CGI
[X] Common HTTP Features

Internet Information Services -> Web Management Tools -> IIS Management Console
[X] IIS Management Console

Download and Install PHP Manager for IIS and the Rewrite Module in this step.


</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/da07fe23-ba4e-4a7f-988f-66dcba52fe10)

Create your PHP Folder under C:\PHP
</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/d4e0c7df-4e41-4cd7-9a40-b1ab76e2cbd1)

Download and Instal Microsoft Visual C++ Redistributable
</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/7ccd157f-59e9-43c2-bf91-57b26ad804bc)

Download and Install MySQL with a typical install.
Create a root password during installation.

</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/b338bfea-b11d-42d9-aef5-492cf9f8d2e4)

Open IIS as an ADMIN and register PHP from within IIS
</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/7aacd69d-b972-4ab0-8b7a-2314ea198f36)

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/77b683d7-99e2-4382-9eee-b31d29f8cb42)

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/0aee1afb-f482-4d07-b41a-abeedf9a6866)




Download osTicket and extract or directly install the files to c:\inetpub\wwwroot
Within c:\inetpub\wwwroot, rename "upload" to "osTicket"
Reload IIS
Go to sites - Default - osTicket and on the right click "Browse*:80"

Some extensuons will not be anabled.
Go back to IIS - sites - Default - osTicket
Click PHP Manager, Enable or Disable an extension and enable the following:
php_imap.dll
php_intl.dll
php_opcache.dll

Refresh osTicket site in your browser.

Rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php

Assign Permissions on ost-config.php - Disable inheritance - Remove All
New Permissions - Everyone - All

Continue installing osTicket from your browser
(Default Email will receive emails from customers)
</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/6501ee88-c618-4a79-9e6f-8cd847c91002)

Download and install HeidiSQL
Create a new session
Use your MySQL username and password and open

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/d9c4435a-8eec-448b-a623-f0bcccf0a1cb)

Create a new Database in Heidi called "osTicket"

Finish your osTicket installation by clicking "Install Now"

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/c35577a1-d333-4aa7-8fd8-e19f74993536)

Clean up:

Delete C:\inetpub\wwwroot\osTicket\setup
Set Permissions to "Read" only on C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />

![image](https://github.com/RafaBelmonte/osticket-prereqs/assets/170759303/9899191f-f846-4bd6-9762-0a36eedcd969)

osTicket should be installed and good to go!
