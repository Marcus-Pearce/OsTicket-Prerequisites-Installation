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

- Create Windows 10 Virtual Machine in Microsoft Azure
- Remote Desktop into Virtual Machine and Enable IIS in Windows
- Install osTicket and it's dependencies
- Clean Up


<h2>Installation Steps</h2>
<p> Start by preparing your environment for the task. Have the Installation Files page open and loaded before proceeding to the next steps.
Installation files-
https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
</p>

<p>
Create an Azure free trial. Upon starting Azure you will have a subscription made for you giving you 200$ in free credits for demo. In reality you will create a new subscription for each department or company to prioritize costs of a service to the approriate account. Go to Virtual Machines and Create a 
Azure Virtual Machine. Make a new Resource group for the VM to belong to. Set the VM's Operating system to Windows 10 with at least 2 Virtual CPUs. Name the VM osTicket and make sure to remember the login details.Check the "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights" box.
</p>

<p>

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/4df16852-94c0-4ed1-95b6-5a304eba7bc4)
</p>

<br />

<p>Let the Virtual Machine create the virtual network and subnet. Azure will validate that the configurations have passed and then click Create.
Allow time for the deployment.

</p>
<p>
  
  ![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/d6769fe1-b85c-4011-9a80-fbfef7c8c811)

</p>
<br />
<p>

After the deployment is finished go to Virtual Machines and copy the Public IP address from the osTicket VM.Open Remote Desktop and paste the Vm's public IP address. Log in using the credential used during creation. Open control panel in the Virtual Machine go to Programs and then "Turn Windows Features on or Off" option. Find Internet Information Services and check the box enabling it.Go to World Web Services and make sure all of the Common HTTP Features are enabled. In Application Development Features Enable CGI. In Web Management Tools make sure IIS Management Console is enabled. Then click okay and let Windows make the changes. To ensure IIS is enabled go to a browser and enter a loopback address(127.0.0.1) to show Internet Information Services page. If page doesn't load, repeat steps.
</p>
<br />

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/b7d08b20-520c-4a89-96c3-4dbb6d3395f2)
<p> Now go back to your main PC and copy the Installation Files URL (https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)  and once back on your VM paste in a new browser. Download and install PHP Manager(PHPManagerForIIS_V1.5.0.msi). Download and install the Rewrite Module(rewrite_amd64_en-US.msi). Create a folder in C: named "PHP". Download  PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip). Unzip the contents into C:\PHP. Download and install  VC_redist.x86.exe. Download and install  MySQL 5.5.62 (mysql-5.5.62-win32.msi). Choose a Typical Configuration and make sure "Launch Configuration Wizard" is checked. Choose Standard Configuration. Make sure to remember the login details created. Enable root access. Launch Internet Information Services as Administrator. Go to the PHP Manager and register the PHP file (php-cgi.exe). file. Restart IIS. Download and install osTicket v1.15.8. Extract and copy “upload” folder to c:\inetpub\wwwroot. Rename the "upload" folder to "osTicket". Restart IIS. Click Browse .80 after going to Sites/ Defaults/osTicket and the site tells you that some extensions are not enabled. </p>

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/5948f2ca-324c-4db2-a4d5-11090fa8d444)

<p>
Go to Sites, Defaults, osTicket and go to the PHP Manager. Click enable or disable an extension and enable "php_imap.dll","php_intl.dll", "php_opcache.dll". Refresh the browser and click continue. Restart IIS for the last time.</p>

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/b623feea-f7c0-4b3c-94dc-ab743dc4d0bf)

Notice the changes after refreshing Browser.
![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/da992219-2295-49c0-93e8-1a84bbb05cf2)





<p>
Disable inheritance by going to the ost-config.php file's Properties, then Security and Advanced. Then remove all inherited permissions from this object. Add a new permission for "Everyone" and set it to full control.

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/adbbe908-d3bc-4842-953c-72e55253d6f9)

</p>

Change C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php.
![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/2c120038-3da5-4ed1-863e-cc1d8e6fea39)

<p>
Download and install HeidiSQL(HeidiSQL_12.3.0.6589_Setup.exe).Open Heidi SQL and create a new session. Connect to the session and create a database called “osTicket”.

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/7776aa04-1c24-4bc1-a7da-fec05a3c1b75)

</p>
<p>
Make sure to remember the "Root" credentials created earlier. The database name has to match the one created in order to work.

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/a3b6e966-d900-4a5d-a658-6d0689d6182f)

</p>
<p>
 Change permission of ost-config.php to remove write access and set to Read only.

![image](https://github.com/Marcus-Pearce/osticket-prereqs/assets/140969692/aa12f3e6-a143-4f94-8145-7c5880c77e2b)

</p>

Delete: C:\inetpub\wwwroot\osTicket\setup folder and you have successfully installed osTicket along with all of its prerequisites.
![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/bedbf321-ee38-45de-91e1-b4bea0408eaa)

