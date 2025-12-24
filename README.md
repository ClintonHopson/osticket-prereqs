<p align="center">
  <img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket help desk logo"/>
</p>

<h1>osTicket – Prerequisites and Installation</h1>

<p>
This tutorial outlines the prerequisites and step-by-step installation of the open-source help desk ticketing system, osTicket.
</p>

<h2>Environments and Technologies Used</h2>

<ul>
  <li>Microsoft Azure (Virtual Machines)</li>
  <li>Remote Desktop Protocol (RDP)</li>
  <li>Internet Information Services (IIS)</li>
</ul>

<h2>Operating Systems Used</h2>

<ul>
  <li>Windows 10 Pro (Version 21H2)</li>
</ul>

<h2>List of Prerequisites</h2>

<ul>
  <li>Azure Virtual Machine</li>
  <li>osTicket Installation Files</li>
  <li>HeidiSQL</li>
</ul>

<h2>Installation Steps</h2>

<p>
  <img src="https://github.com/user-attachments/assets/d567bc53-7bcd-498d-9ac2-e1df0ac851fa" alt="Azure portal showing virtual machine creation screen"/>
</p>

<p>
First, create a new Azure Virtual Machine. Name it something descriptive, such as <strong>osTicket-VM</strong>.  
Select <strong>Windows 10 Pro</strong> with <strong>2 vCPUs</strong>, check the licensing confirmation box, and proceed with creating the VM.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/b5a7a6b2-8d84-40fd-ad6c-49eb55e17560" alt="Azure virtual machine deployment summary"/>
</p>

<p>
Once the VM deployment is complete, open the Remote Desktop application and connect using the VM’s public IP address.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/abdf36e1-33ad-4318-9c4e-162d47c593e8" alt="Remote Desktop connection window with IP address entered"/>
</p>

<p>
After logging into the VM, locate the osTicket installation files, unzip them, and begin the installation process.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/893da4c1-49ee-4e0f-ba6d-70b495712f7c" alt="Extracted osTicket installation files"/>
</p>

<p>
Enable IIS by opening the Control Panel and selecting <strong>Turn Windows features on or off</strong>.  
Locate <strong>Internet Information Services (IIS)</strong>, enable it, then navigate to:
</p>

<p>
<strong>World Wide Web Services → Application Development Features → CGI</strong>
</p>

<p>
Enable CGI and click <strong>OK</strong> to apply the changes.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/dc04267c-9a3f-451a-b7f4-f139f16baf6e" alt="Windows Features menu with IIS and CGI enabled"/>
</p>

<p>
Next, install <strong>PHP Manager for IIS</strong> by right-clicking the installer and selecting <strong>Install</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/66e6c304-4814-43aa-a8f0-3886bcc49fc8" alt="PHP Manager for IIS installation window"/>
</p>

<p>
Install the <strong>URL Rewrite Module</strong> and configure the environment as required.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/3da785e6-c409-4b5a-b71b-b2c487c1d7b5" alt="IIS URL Rewrite module installation screen"/>
</p>

<p>
Create a new folder named <strong>PHP</strong> in the root of the <strong>C:\</strong> drive.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/38f22ee2-d8e6-4560-98c6-1368bd1e8205" alt="C drive directory showing newly created PHP folder"/>
</p>

<p>
Locate <strong>php-7.3.8-nts-Win32-VC15-x86.zip</strong>, extract it, and move its contents into the newly created <strong>C:\PHP</strong> directory.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/f790415d-ac80-4161-8744-c2cfd6e1293a" alt="Extracted PHP files inside C PHP directory"/>
</p>

<p>
Install <strong>VC_redist.x86.exe</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/51616472-1c9f-47f2-bc4a-30e0574c5f1f" alt="Visual C++ Redistributable installation window"/>
</p>

<p>
When prompted for database credentials during setup, use <strong>root</strong> as both the username and password for this lab environment, then click <strong>Execute</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/6957f61c-e505-44e4-9918-77407e8b61ec" alt="Database credential prompt during installation"/>
</p>

<p>
Open <strong>IIS Manager</strong> as an administrator.  
Select <strong>osTicket</strong>, then open <strong>PHP Manager</strong> and register the <strong>php-cgi.exe</strong> file.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/a6f0bdfe-ce33-472d-b771-42f494ede237" alt="IIS Manager showing PHP Manager configuration"/>
</p>

<p>
Restart the IIS server to apply the changes.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/2c744605-0ba4-4233-9ad2-2585b4e59f40" alt="IIS Manager restart option selected"/>
</p>

<p>
Extract <strong>osTicket v1.15.8</strong> and copy all contents into:
</p>

<p><strong>C:\inetpub\wwwroot</strong></p>

<p>
Rename the folder to <strong>osTicket</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/6b8cf0df-475b-4d7f-a26f-556086ddee1b" alt="osTicket files placed in wwwroot directory"/>
</p>

<p>
In IIS Manager, navigate to:
</p>

<p>
<strong>Sites → Default Web Site → osTicket → Browse</strong>
</p>

<p>
  <img src="https://github.com/user-attachments/assets/dc199fee-a10b-463b-bc30-a8496dd57718" alt="IIS Manager site tree highlighting osTicket"/>
</p>

<p>
Within PHP Manager, enable the required PHP extensions, restart the server, and verify they are enabled.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/2253f4bd-5db2-4345-b264-b556d9fa85a0" alt="PHP extensions enabled in PHP Manager"/>
</p>

<p>
Navigate to:
</p>

<p>
<strong>C:\inetpub\wwwroot\osTicket\include</strong>
</p>

<p>
Rename <strong>ost-sampleconfig.php</strong> to <strong>ost-config.php</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/322b7bef-06a7-47f0-951b-2469a06550f8" alt="Renamed ost-config PHP file"/>
</p>

<p>
Right-click the file, open <strong>Properties → Security</strong>, disable inheritance, and remove all existing permissions.
</p>

<p>
Grant <strong>Everyone</strong> full control.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/7d7f1343-efce-4280-b511-925467c77822" alt="Windows security permissions configuration"/>
</p>

<p>
Continue the osTicket web-based setup by clicking <strong>Continue</strong>.  
Assign a help desk name and configure a default email address for ticket notifications.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/328cb5fb-56d1-4d7d-9094-f811b0ee0bdf" alt="osTicket web installer configuration screen"/>
</p>

<p>
Install <strong>HeidiSQL</strong>, open the application, and create a new session using <strong>root</strong> as the username and password.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/4e707867-417e-44a7-844a-af836f3216ee" alt="HeidiSQL main interface"/>
</p>

<p>
Create a new database named <strong>osTicket</strong>.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/696f5936-51d5-4884-bd8d-be2bde387391" alt="HeidiSQL database creation screen"/>
</p>

<p>
Select <strong>Continue</strong> to complete the installation.
</p>

<p>
  <img src="https://github.com/user-attachments/assets/82dc5461-5b0b-4e03-92c5-cb4ddff9bab4" alt="Final osTicket installation confirmation screen"/>
</p>

<p>
<strong>Congratulations!</strong> You have successfully installed osTicket.  
Additional configuration can be performed to assign user roles and permissions, but the core ticket creation and resolution system is now operational.
</p>
