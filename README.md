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
Azure Virtual Machine. Make a new Resource group for the VM to belong to. Set the VM's Operating system to Windows 10 with at least 2 Virtual CPUs. Name the VM osTicket and make sure to remember the login details.
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
<p> Change the ost-config.php file's permissions back to read access only. After using the service delete the C:\inetpub\wwwroot\osTicket\setup folder. </p>

![image](https://github.com/Mrpearce92/osticket-prereqs/assets/140969692/bedbf321-ee38-45de-91e1-b4bea0408eaa)

