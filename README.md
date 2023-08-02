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

![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/4df16852-94c0-4ed1-95b6-5a304eba7bc4)



<p>


</p>
<p>
After making your subscription go to Virtual Machines and Create a Virtual Machine running Windows 10 with at least 2 Virtual CPUs.
</p>
<br />


<p>



</p>
<p>
  
  ![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/d6769fe1-b85c-4011-9a80-fbfef7c8c811)

</p>
<br />

<p>
<p>
  Remote into the VM and enable IIS in Windows. Turning on CGI and the remaining unchecked from Common HTTP Features. Then install all dependencies need for OsTicket and then install OsTicket
</p>
<br />

![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/b7d08b20-520c-4a89-96c3-4dbb6d3395f2)
<p> Change the ost-config.php file's permissions back to read access only. After using the service delete the C:\inetpub\wwwroot\osTicket\setup folder. </p>

![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/74e4ece4-6b4a-4d54-bd26-e400b46c746c)
