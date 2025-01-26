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
<br />
<p>
  
![image](https://github.com/user-attachments/assets/190e832e-c429-427c-8899-b98e53a5d603)
  
</p>
<p>
Now within the VM we are going to download the osTicket installation files and upzip them onto the desktop. These files are going to be used to install osTicket on the VM.
This link will provide you with all the resources you will need to install osTicket. https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6.
<p>

![image](https://github.com/user-attachments/assets/c5b3ad78-2009-4338-9f3d-c0c1f5f4f0dc)


  
</p>
<p>
We will now enable IIS(Internet Information Services) which is a web server software, it allows you to deploy and manage websites. We are also going to enable CGI(Common Gateway Interface), this interface helps web servers to interact with other software like scripts. So to enable them you are going to navigate to the control panel > click on uninstall a program. Then on the left side of the screen you're going to click Turn Windows features on or off. When a window pops up, you're going to check the box that has IIS(Internet Information Services). You will now expand the IIS box and navigate to CGI as follows. World Wide Services > Applications Development Features > CGI.
</p>
<br />

![image](https://github.com/user-attachments/assets/86cdebcb-b0eb-450d-a2d3-7d74b9e55fe8)


![image](https://github.com/user-attachments/assets/28ed1b7a-7239-48ee-8407-8d44ba47407b)

