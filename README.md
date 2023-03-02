<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. This tutorial of osTicket will be inside of a Windows 10 Microsoft Azure virtual machine. This was designed for beginners to learn how to setup and use osTicket. In a real world environment, there is going to be a little more customiztion depending on the company, so I wouldn't suggest using this tutorial to setup for an actual company, but rather to learn from.
<br />

<h2>Environments and Technologies Used</h2>

- HeidiSQL
- Internet Information Services (IIS)
- Microsoft Azure (Virtual Machines/Compute)
- osTicket
- Remote Desktop

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Using Remote Desktop Protocol into your Windows 10 virtual machine
- Install / Enable IIS in Windows with CGI
- Download and install PHP Manager for IIS
- Download and install the Rewrite Module
- Create the directory C:\PHP
- Download PHP 7.3.8 and unzip the contents into C:\PHP
- Download and install VC_redist.x86.exe
- Download and install MySQL 5.5.62
- Open IIS as an Admin and register PHP from within IIS
- Install osTicket v1.15.8
- Download and install HeidiSQL
- Continue setting up osTicket in the browser

<h2>Installation Files Used</h2>

- HeidiSQL
- mysql
- osTicket
- php
- PHPManagerForIIS
- rewrite_amd64
- VC_redist.x86

<h2>Installation Steps</h2>

</p>
  
We will first open Remote Desktop Connection from our computer. Make sure to copy the Public IP address from our Virtual Machine we created in Microsoft Azure and connect with RDP with your credentials. You may get a popup regarding identity verification of the remote computer not being verified, go ahead and click "Yes" to proceed.

<p>
<img src="https://i.imgur.com/Znn2VTZ.png"/>
</p>

<p>
<img src="https://i.imgur.com/L0O1ZD6.png"/>    
</p>

<p>
<img src="https://i.imgur.com/SYY7Imv.png"/>    
</p>

When you log on to your virtal machine, you can mark everthing as "No" for your privacy settings. You you then want to the open up a browser and make sure you paste the following Google Drive folder link to download your installation files:
**[https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)**

<p>
<img src="https://i.imgur.com/T7bTeff.png"/>
</p>

Go to the Control Panel > Programs > and click on "Turn Windows features on or off" 

<p>
<img src="https://i.imgur.com/IoMFNcx.png"/>
</p>

Install / Enable IIS in Windows WITH CGI

Make sure you turn on Internet Information Services by clicking on the box and then expanding it, and then expanding World Wide Web Services, and then expanding Application Development Features and then click and check CGI.

<p>
<img src="https://i.imgur.com/ErqSDhw.png"/>
</p>

Click OK and wait for everything to install and apply changes.
  
<p>
  
If you want to test if your web servers are working, you can open a new browser and type in 127.0.0.1 (this is your local host or loopback). You should be able to see the IIS page popup. If not, make sure you actually installed IIS with CGI.
  
</p>

<p>
<img src="https://i.imgur.com/fHwppgF.png"/>
</p>

<p>
We will now download and install PHP Manager for IIS and the rewrite_amd64 files from the Google Drive folder and create a new directory called C:\PHP
</p>

<p>
<img src="https://i.imgur.com/HhuO7jc.png"/>
</p>

<p>
Now we will download, install, and extract the php-7.3.8-nts-Win32-VC15-x86.zip file into our new C:\PHP folder
</p>

<p>
<img src="https://i.imgur.com/JQZno4p.png"/>
</p>

<p>
<img src="https://i.imgur.com/pnybEfG.png"/>
</p>

<p>
Next we will download and install VC_redist.x86.exe.
</p>
  
<p>
<img src="https://i.imgur.com/2i3Ev2W.png"/>
<p>  

Then we will download and install mysql-5.5.62-win32.msi. For the mysql .msi file, make sure you choose "Typical" installation and make sure the "Launch the MySQL Instance Configuration Wizard" box is checked off before you click "Finish". 
  
<p>
<img src="https://i.imgur.com/6t7eIFm.png"/>
<p>
  
<p>
<img src="https://i.imgur.com/BGPTVWT.png"/>
<p>

<p>
You will now want to choose Standard Configuration, click "Next", Password1 will be your "New root password" (root will be the username, however, you don't need to set that up), click "Execute", and click "Finish".
<p>
  
<p>
<img src="https://i.imgur.com/QSAB1Cb.png"/>
<p>
 
<p>
<img src="https://i.imgur.com/j7V5VVJ.png"/>
<p> 

<p>
<img src="https://i.imgur.com/nmxzVpB.png"/>
<p>  
  
<p>
<img src="https://i.imgur.com/3OT8IWD.png"/>
<p>  
   
We will go to the Start menu and search for IIS and open it as an administrator and click on the "PHP Manager" icon" and then click on "Register new PHP version", browse to find you PHP folder, and look for your php-cgi file and open it and click "OK".
  
<p>
<img src="https://i.imgur.com/UUx6oss.png"/>
<p>  

<p>
<img src="https://i.imgur.com/4neNZh1.png"/>
<p>     
  
<p>
<img src="https://i.imgur.com/fs0E8LF.png"/>
<p>    
  
<p>
<img src="https://i.imgur.com/T9h1Ifn.png"/>
<p> 

Make sure you reload IIS by clicking on your local host server "VM-osTicket" and clicking "Restart" under Manage Server.

<p>
<img src="https://i.imgur.com/uUEWqn8.png"/>
</p>

We will now download osTicket from our Installation Files Folder, Extract and copy the “upload” folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename the “upload” folder to “osTicket”. To do this, you will want to open two separate File Explorer windows. On one, navigate to the Downloads folder and double click the "osTicket-v1.15.8". There, you will find the "upload" folder. On the other window click on Windows (C:) drive, locate the "inetpub" folder and open it.

<p>
<img src="https://i.imgur.com/A6gWKpP.png"/>
</p>
<p>

Once you open the inetpub folder, look for and open the wwwroot file. This is where you'll be dragging the upload file into. Give it a few to finish copying and make sure you rename the file to osTicket.

<p>
<img src="https://i.imgur.com/POE7Wx1.png"/>
</p>

<p>
<img src="https://i.imgur.com/Gp6BPrD.png"/>
</p>

<p>
Restart the IIS server.
</p>

<p>
<img src="https://i.imgur.com/uUEWqn8.png"/>
</p>

<br />

Exand VM-osTicket > Sites > Default Web Site > Click on osTicket > Click on Browse *:80 (http)

<p>
<img src="https://i.imgur.com/3yhWgfD.png"/>
</p>

You will now see the osTicket Installer in your browser

<p>
<img src="https://i.imgur.com/B4HD7J7.png"/>
</p>

<br />

We are going to enable some additional extensions in IIS. Go back to IIS Manager and expand VM-osticket > Sites > Default Web Site > click osTicket > double click on PHP Manager > click "Enable or disable an extension". 

<p>
<img src="https://i.imgur.com/WSzZh2h.png"/>
</p>
<p>
  
Locate and enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll". You can enable them each by right-clicking and selecting "Enable".
</p>tin
  
<p>
<img src="https://i.imgur.com/k27l39y.png"/>
</p>
<p>

Refresh the osTicket installer page and observe the changes, it should match the picture below.
<p>
<img src="https://i.imgur.com/dk6kFAu.png"/>
</p>
<p>

<p>
<img src=""/>
</p>
<p>

<p>
<img src=""/>
</p>
<p>


<br />

<p>
<img src="https://i.imgur.com/W67FgEV.png"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/uEMoIah.png"/>
</p>
<p>
In file explorer go to C: -> inetpub-> wwwroot -> osTicket -> include, then locate ost-sampleconfig.php at the bottom.
</p>
<br />

<p>
<img src="https://i.imgur.com/T4CBoq4.png"/>
</p>
<p>
Then rename the file form "ost-sampleconfig.php" to "ost-config.php"
</p>
<br />

<p>
<img src="https://i.imgur.com/Xto4OTI.png"/>
</p>
<p>
Then right click on that file got to Properties -> Security -> Disable inheritance -> Remove all
</p>
<br />

<p>
<img src="https://i.imgur.com/KTIJ5J0.png"/>
</p>
<p>
Then click Add -> Select a principal -> In the object box type "Everyone" and check for names -> click OK
</p>
<br />

<p>
<img src="https://i.imgur.com/7Tpm1LY.png"/>
</p>
<p>
Select Full control and hit OK -> click Apply -> OK -> OK
</p>
<br />

<p>
<img src="https://i.imgur.com/9Bf1IuO.png"/>
</p>
<p>
Now go back into the osTicket installer in the browser and click continue.
</p>
<br />

<p>
<img src="https://i.imgur.com/3uOvZ8X.png"/>
</p>
<p>
For the name I just did "Helpdesk" and for the email I did "john@helpdesk.com", then I set the Admin User credentials, write these down if you made up your own. 

Now just leave this page be and go onto the next step in this tutorial.
</p>
<br />

<p>
<img src="https://i.imgur.com/3d9To5Z.png"/>
</p>
<p>
Download HeidiSQL form the Drive folder, it will download as a word doc and open it, then click the link to download the HeidiSQL Setup. 

Then install it.

Once it opens, click the green new button in the bottom left of the window, the username should be "root" and the password should be "Password1" if you set them to those earlier in this tutorial, then hit open.
</p>
<br />

<p>
<img src="https://i.imgur.com/8IMqLza.png"/>
</p>
<p>
In HeidiSQL, right click Unnamed -> Create new -> Database, name it "osTicket" and click OK
</p>
<br />

<p>
<img src="https://i.imgur.com/qmZlp4P.png"/>
</p>
<p>
Going back into the osTicket installer in the browser, put in the username and password for MySQL (should be "root" and "Password1" if you set them to those) and click install.
</p>
<br />

<p>
<img src="https://i.imgur.com/hoVuqRf.jpg"/>
<img src="https://i.imgur.com/I8ZApOx.png"/>
</p>
<p>
Now that it has installed, open up both of these urls in your VM's browser

- Help desk login page (login with the credentials that you set for the admin user for osTicket): http://localhost/osTicket/scp/login.php

- End Users osTicket URL: http://localhost/osTicket/ 
</p>
<br />

<p>
<img src="https://i.imgur.com/GanOWok.png"/>
</p>
<p>
We are almost ready to go on to the next tutorial, but first we need to clean some things up.

First browse to the C: drive -> inetpub -> wwwroot -> osTicket -> and delete the "setup" folder.
</p>
<br />

<p>
<img src="https://i.imgur.com/ZEWbk8x.png"/>
</p>
<p>
Now browse to C: -> inetpub -> wwwroot -> osTicket -> include -> and locate ost-config.php

Then on ost-config.php go to Properties -> Security -> Advanced -> click Everyone -> Edit -> and set the permissions to Read and Read & Execute only -> Apply.

Click OK.

Congratulations, you have made it to the end of this part of the tutorial! Now keep the VM and osTicket open, then move on to the post installation setup tutorial.
The link to that tutorial is linked below.

- [osTicket: Post-Installation Configuration](https://github.com/jacksonma
