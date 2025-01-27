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

- Windows 10</b>


<h2>Installation Steps</h2>
In this tutorial I'm going to walk you through on how to create a virtual machine, install a ticketing system, and setup SQL(Structured Query Language).
<p>
<br />
  
First we will need to create a resource group and a VM(virtual machine) in Microsoft Azure. The reason we are using a VM is because it allows us to safetly install the ticketing system, all while keeping our physical machine protected. In some cases it is also cost-effective.
<p>
<br />
<p>
  
![image](https://github.com/user-attachments/assets/4ee9145c-4e0b-4daa-b872-8921b8141882)

</p>
<p>
Next you will connect your VM using RDP(Remote Desktop Protocol), which allows you to remotely connect to devices on a network. You will use the VM's public IPv4 address to connect. If you're using a Mac you will need to download the Windows App and then connect your VM.
</p>

  
![image](https://github.com/user-attachments/assets/190e832e-c429-427c-8899-b98e53a5d603)
  
</p>
<p>
Now within the VM we are going to download the osTicket installation files and upzip them onto the desktop. These files are going to be used to install osTicket on the VM.
This link will provide you with all the resources you will need to install osTicket. https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6.
<p>

![image](https://github.com/user-attachments/assets/c5b3ad78-2009-4338-9f3d-c0c1f5f4f0dc)

<br />
  
</p>
<p>
We will now enable IIS(Internet Information Services) which is a web server software, it allows you to deploy and manage websites. We are also going to enable CGI(Common Gateway Interface), this interface helps web servers to interact with other software like scripts. So to enable them you are going to navigate to the control panel > click on uninstall a program. Then on the left side of the screen you're going to click Turn Windows features on or off. When a window pops up, you're going to check the box that has IIS(Internet Information Services). You will now expand the IIS box and navigate to CGI as follows. World Wide Services > Applications Development Features > CGI.

<br />

![image](https://github.com/user-attachments/assets/86cdebcb-b0eb-450d-a2d3-7d74b9e55fe8)


![image](https://github.com/user-attachments/assets/28ed1b7a-7239-48ee-8407-8d44ba47407b)

<br />

From the osTicket folder, we are going to install PHP Manager for IIS, Rewrite Module, VC redist and MySQL 5.5.62. These are some of the requirements needed to have osTicket run smoothly. Then we will create a new folder named PHP and unzip the PHP 7.3.8 files from the osTicket installation folder into the new PHP folder.


![image](https://github.com/user-attachments/assets/239feb65-9801-47bd-b5fa-1d298fd0d0d7)

<br />

Next we will install osTicket from the osTicket installation files folder and extract the files. Copy the "upload" folder to C:\inetpub\wwwroot, then rename the folder to "osTicket."

<br />

![image](https://github.com/user-attachments/assets/2d7a937d-c3cd-4843-8da4-bf2d5a99f3a5)
<br />




We will now load the osTicket site in our web browser. Open the IIS manager and restart the server. Then in IIS manager you will navigate to Sites > Default > osTicket. On the right will click “Browse *:80” and that will open the osTicket web browser.
<br />


![image](https://github.com/user-attachments/assets/e5f389d4-9e33-4a52-970a-eb4d019097ff)
<br />


Then we will go back into IIS manager and enable some extentions that was not enabled upon startup. Navigate to Sites > Default > osTicket, double click on PHP manager. Then select enable or disable an extention. From there you will find the extentions,  php_imap.dll, php_intl.dll, php_opcache.dll, you will right click them and click enable.
<br />


![Screen Shot 2025-01-26 at 9 26 25 PM](https://github.com/user-attachments/assets/25dd94e1-4e48-42cd-beb4-5b39a44c0cc4)
<br />


Now we're going to rename a file that's inside the osTicket folder which is (C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php) to (C:\inetpub\wwwroot\osTicket\include\ost-config.php). Then we will make sure osTicket has access to make changes to this folder as well. To do this we will disable inheritance from the Advanced Secrity Settings section in the ostconfig.php file and set new permission to grant to full access to "everyone."


![image](https://github.com/user-attachments/assets/bccd2cad-e4cd-4a6a-a5ca-f31300370543)


Next we will continue setting up osTicket by clicking continue. Then fill out all information to your desired preference. We will also download HeidiSQL from the osTicket installation folder. This application will allow us to make a connection with our database.
<br />


![image](https://github.com/user-attachments/assets/be5a2423-dde6-4797-96e2-5e6ca30c7134)


Now we're going to make a connection and setup a database named osTicket using HeidiSQL. So we will launch HeididSQL, create a new session and use "root" as the username and password. Then we will click open to connect to the database and create a database called osTicket.


![image](https://github.com/user-attachments/assets/5cb73461-1b92-4dfb-8abb-6d09ae3f678c)


Next we will process to setting up osTicket in the browser. You will continue to fill out the database section as follows, 

MySQL Database: osTicket 

MySQL Username: root 

MySQL Password: root

Then you will click "Install Now", if everything went as planned you will now have osTicket installed. Congratulations!!!!


![image](https://github.com/user-attachments/assets/086da4d4-760a-4b10-a904-f99dfa0b904c)
