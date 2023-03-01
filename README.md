<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket. This tutorial of osTicket will be inside of a Windows 10 Microsoft Azure virtual machine. This was designed for beginners to learn how to setup and use osTicket. In a real world environment, there is going to be a little more customiztion depending on the company, so I wouldn't suggest using this tutorial to setup for an actual company, but rather to learn from.<br />

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



Make sure you paste the following Google Drive folder link to the browser in the virtual machine:
https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<p>
<img src="https://i.imgur.com/55R6cCS.png"/>
</p>
<br />

<p>
<img src="https://i.imgur.com/mpO8frk.png"/>
</p>
<p>
Go to the Programs section in Control Panel and click on "Turn Windows features on or off".
</p>
<br />

<p>
<img src="https://i.imgur.com/7GVFsMN.png"/>
</p>
<p>
Install / Enable IIS in Windows WITH CGI

Just make sure every box that is shown in the image above is checked, you can hit the little "+" to expand menus out.

Hit OK and wait for everything to install and apply changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/U7RUUyI.png"/>
</p>
<p>
Now in a new browser tab, type 127.0.0.1 (this is your loopback IP, if you don't know what that is google it). You then should see the IIS page popup, if you don't, go back and make sure you actually installed IIS with CGI.
</p>
<br />

<p>
<img src="https://i.imgur.com/Xx05Dva.png"/>
</p>
<p>
Now from the drive folder install PHPManagerForIIS_V1.5.0.msi and rewrite_amd64_en-US.msi
</p>
<br />

<p>
<img src="https://i.imgur.com/No25WUQ.png"/>
</p>
<p>
Create a new directory called C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/IA8113C.png"/>
</p>
<p>
Now install php-7.3.8-nts-Win32-VC15-x86.zip, move and extract all the contents into C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/PZ3BXsF.png"/>
</p>
<p>
Download and install VC_redist.x86.exe.

Download and install mysql-5.5.62-win32.msi
- Typical Setup ->
- Launch Configuration Wizard (after install) ->
- Standard Configuration ->
- Next ->
- Password1 (root will be the username, but you don't need to set that up) ->
- Execute 

</p>
<br />

<p>
<img src="https://i.imgur.com/kfk7PPp.png"/>
</p>
<p>
Open IIS as administrator as shown above.
</p>
<br />

<p>
<img src="https://i.imgur.com/QnWyh4t.png"/>
</p>
<p>
After opening IIS Manager as admin, click on the "PHP Manager" icon", hit "Register new PHP version". 

Browse files and find the PHP folder we made earlier and select "php-cgi" and hit open.
</p>
<br />

<p>
<img src="https://i.imgur.com/7nygYZ7.png"/>
</p>
<p>
Restart the IIS server as per the image above.
</p>
<br />

<p>
<img src="https://i.imgur.com/VCrGYgY.png"/>
</p>
<p>
Now open two separate file explorer windows and on one navigate to the downloads folder and click on osTicket-v1.15.8, and on the other window open up your C:/ drive.
</p>
<br />

<p>
<img src="https://i.imgur.com/izvuG0n.png"/>
</p>
<p>
In that C:/ window, navigate to "inetpup" -> "wwwroot" and move in the "upload" folder from the osTicket zip and let it finish copying. Then rename the "upload" folder to "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/RxeVUCO.png"/>
</p>
<p>
Restart the IIS server.
</p>
<br />

<p>
<img src="https://i.imgur.com/fm1ZFgU.png"/>
</p>
<p>
Close and reopen IIS manager as admin again, on the left expand the menus osTicket-VM -> Sites -> Default Web Site -> then click on osTicket.

On the right hit Browse *:80 and you should see the osTicket installer open inside of your default browser.
</p>
<br />

<p>
<img src="https://i.imgur.com/QqUA0PL.png"/>
</p>
<p>
Go back to IIS Manager, osTicket-VM -> Sites -> Default Web Site -> click osTicket, then click on "Enable or disable an extension".
</p>
<br />

<p>
<img src="https://i.imgur.com/PTOgAhg.png"/>
</p>
<p>
Locate "php_imap.dll", "php_intl.dll", and "php_opcache.dll". Enable them all by right-clicking.
</p>
<br />

<p>
<img src="https://i.imgur.com/W67FgEV.png"/>
</p>
<p>
Refresh the osTicket installer page and observe the changes, it should match the picture above.
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
