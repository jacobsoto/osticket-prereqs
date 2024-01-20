<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Modual 
- VC Redlist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads
  https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
<h2>Installation Steps</h2>

<p>
</p>
<p>  
 -- The first step to Instaling osTicket is creating your virtual machine using Azure. 
set up your virtual machine by using Windows 10 Pro and make sure its using atleast two vcpus.

-- Once you created your virtual machine connect to it using the Remote desktop connection application that is already pre installed on to your computer. To do this you will need to copy the public IP address and paste it into Remote desktop application.

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/7fed1a55-8b61-4c53-a96f-5c69ce25f192)

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/481a5972-8f56-4133-a167-3cb20f6a17df)

--After we have connected to our virtual machine we will be enabling IIS in Windows. To do this we will need to open control panel and from control panel we will select programs.  


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/1a2a34fb-e8c5-432f-9af3-f9b39a6599d5)

--Then select turn window features on or off
![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/3b3a603b-bc8c-4921-bee7-dfff580fcfb1)

-- after we scroll for a bit we will find a option that says "internet information services" we will select the box and it will expand

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/871a0997-7969-4b36-ba06-043ce46563a3)


--after it expands we will need to press the box that says world wide web services then press application development then check the box that says CGI 
NOTE please make sure all Common HTTP Features are checked.

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/fe31c203-eca6-470a-bd9d-4a20b3bf74f8)

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/a6b48b29-6bcd-4baf-93e3-6d2857ffad4d)


--To make sure IIS is installed please type 127.0.0.1 into the search bar on any internet browser, it should look like this 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/0a77b4e5-aff9-403a-a69e-2f274af4ff78)


--Next step will be to download PHP manager from the installation files please click the link to get access to these files.

--please click through until it lets you download the file

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/2f01aeae-0b52-4d62-991a-c3d70af3a2ea)

-- Next please install the Rewrite Modual from the Installation files.

-- create a folder in the c drive called PHP 

-- From installation files download PHP 7.3.8 and unzip the the contents in c:/PHP

-- Once we extracted all the files into the c drive we will want to go ahead and install the VC_redist.x86.exe file from the installation files. Go through the setup wizzard and finish setting VC_redist.x86.exe.

-- After this please download MYSQL 5.5.62 run the set up wizzard press typical setup then launch configuration wizard. 

after we set this up will want to make the root password. please make this password super simple so you do not forget. I will be using Password1


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/ba408263-b247-40dd-81cf-a38c3dba2794)

execute the process on the next page 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/f53f3744-acb0-4c81-9044-58164e739b77)

now that we have the files installed we will search for IIS in the search bar. open IIS as and administrator 
 The program should look like this.

 ![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/8a09ab5e-0530-479b-b2db-c6574e5d89f9)

 we will now register PHP from within IIS. click on php manager 

 ![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/eeac39d7-4188-4f58-9936-60591639c282)

 then register new PHP version

 ![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/e163fab7-716d-47a3-91f3-e1c2f7b2519e)

you will now need to provide a path to the php file (php-cgi.exe). Go to C Drive -> PHP -> click on php-cgi file.

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/32e28ff7-b710-4c81-bf6a-6cf12399763d)

when you add or remove things to a IIS server you should do a restart, here is how you do it. click on the name of the server  and on the right press restart 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/39d2daed-162a-4f78-ad45-779eb89922e5)

Now that we got everything out of the way we will finally be able to install osTicket. Please select the osTicket file from the installation list and download it.
once it is download please extract and copy "upload" folder to c:/inetpub/wwwroot within c:\inetpub\wwwroot, rename "upload" to "osTicket"

you will want to restart the IIS server after you have completed this step.

after you have restarted the server you will want to open IIS again and click on go to sites then click OsTicket then on the right press *80

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/b27d6c8b-ef10-4315-abc3-c816415bce6a)


after you have done the previous steps a window should open looking like this 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/3f944905-6bf7-4535-9095-112347a3421c)

as you see in the image we can see some red marks. this means some extensions are not enabled so we will need to enable them.

to do this we need to go back to IIS and click sites --> default webstore --> OsTicket --> php manager 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/012d9130-f139-4c56-a663-90ccb21a0229)

when php manager opens we will press enable or disable an extension

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/6e8315e6-c6ac-43c3-866e-8173e82c8195)

now that we got to this page here are a list of extensions we need to enable to get OsTicket to work

Enable: php_imap.dll

Enable: php_intl.dll

Enable: php_opcache.dll

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/83025c8c-e3be-4225-811d-fffc42baf993)


next we need to Rename: ost-config.php

From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/fd434202-77c9-4add-a71f-69c882c66fd8)


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/59799cea-0894-470d-8aaa-fc79d1e609d6)


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/5a91d11f-de16-4327-8e02-bc0afff03ff8)

next we need to set permissons for the file ost-config so that anyone can change the file. right click the file and select properties


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/946a9b52-82fb-4dc7-9282-45c3b79ad711)


go to securtiy and press advanced 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/73c98554-71b3-4c08-ba07-d92ff0bb3051)


then we will select disable inheritince 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/68ce3b23-f30e-4cd7-a515-c4e6f61aca3c)

then we will select remove all inherited permissions 

 ![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/1e65e3e2-2aa8-45e7-8a8a-521c9c8c0378)

 now from this please press the add button then press select a principal we will then type "everyone" then press ok

 ![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/30910b7a-95f5-4c60-83cc-49ad3e3a5155)

and for now we will give "everyone" full control

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/777846c7-7e64-403d-b003-309f38bdc667)

we will continue setting up osTicket in the browser 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/bfcf8a5a-a4c1-4cfe-bcfa-8cfb674ffd9b)


NOTE* please write the user name and passwords down so you do not forget.

next we will need to install the HeidiSQL

From the Installation Files, download and install HeidiSQL.

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/82936d57-5912-4460-92b4-ea88ea96dd47)

Open Heidi SQL

Create a new session, root/Password1


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/8800b799-07d5-447e-b2f5-9fe46923c34b)

we will now continue this on the os ticket browser

osticket will now ask you for the username and password you had just created

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/014c1811-6833-4028-b36e-983cea01b389)

after doing this we need to back to heidi and create a data base called osTicket. we do this by right clicking unamed then press create new then database then name is osTicket

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/d97eafc8-fe47-4e82-8296-e91e31d0f3b0)

after we have created our data base we can finally press install now on osTicket.

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/1a6a20e2-5208-4ced-aadf-3a228f24421f)

the last step is to do some clean up. we will want to delete the setup folder in our system C:\inetpub\wwwroot\osTicket\setup.

only delete the set up folder and nothing else 

We then will want to set the permissions back to "Read" only in the ost-config.php file.

Click on edit

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/b7c0962c-3f54-43f0-8440-be6edcc0e231)

Then this will take you to permissions and just uncheck the boxes 

![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/6d3da5c4-094b-4771-8335-0d99b03c25bb)




Now just log into osTicket.


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/a5828f72-1b90-486d-8796-e754d27628b4)



congratulations you are now complete


![image](https://github.com/jacobsoto/osticket-prereqs/assets/156248197/0f64f125-de5f-46ad-9d7e-6e1b1f448d49)















 
 






































