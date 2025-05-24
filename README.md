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

- Item 1 : Azure Virtual Machine
- Item 2 : osTicket Installation Files
- Item 3 : Heidi SQL


<h2>Installation Steps</h2>

<p>

   ![image](https://github.com/user-attachments/assets/d567bc53-7bcd-498d-9ac2-e1df0ac851fa)


</p>
<p>
Ok so 1st you will create a Virtual Machine, make sure you name it Os-TicketVM or something of the sort. For your image, you will select Windows 10 Pro with two vCPUs after this, check the copyright box at the bottom and skip to create VM
<br />

<p>

   ![image](https://github.com/user-attachments/assets/b5a7a6b2-8d84-40fd-ad6c-49eb55e17560)
 

</p>
<p>
Then, once the VM is done creating, go ahead and open your remote desktop app and enter in the VM's IP addres 
</p>
<br />


   ![image](https://github.com/user-attachments/assets/abdf36e1-33ad-4318-9c4e-162d47c593e8)

  
</p>
<p>
After you are logged into the VM we will go to the installation file for Os-Ticket and unzip that file and start the installation process



![image](https://github.com/user-attachments/assets/893da4c1-49ee-4e0f-ba6d-70b495712f7c)



Then enable IIS by opening the control panel and going to " Turn Windows Features On or Off". Then scroll down to locate ISS select the box next to it then expand this section and go to Word Wide Web services > Application Develpoment Features > CGI and selecte CGI then click OK to confirm these changes. 



  ![image](https://github.com/user-attachments/assets/dc04267c-9a3f-451a-b7f4-f139f16baf6e)




Next install PHP manager just right click and install nothing special to do here. 



  ![image](https://github.com/user-attachments/assets/66e6c304-4814-43aa-a8f0-3886bcc49fc8)






Next install the rewrite module and configure the enviroment



  ![image](https://github.com/user-attachments/assets/3da785e6-c409-4b5a-b71b-b2c487c1d7b5)




Then create a folder in your maiun C drive on the computer labed PHP 



![image](https://github.com/user-attachments/assets/38f22ee2-d8e6-4560-98c6-1368bd1e8205)




Locate the "PHP 7.3.8 php-7.3.8-nts-Win32-VC15-x86.zip" unzip it and move its contents to the PHP file you made on your C Drive




![image](https://github.com/user-attachments/assets/f790415d-ac80-4161-8744-c2cfd6e1293a)




Next install the VC_redist.x86.exe 




![image](https://github.com/user-attachments/assets/51616472-1c9f-47f2-bc4a-30e0574c5f1f)








![image](https://github.com/user-attachments/assets/6957f61c-e505-44e4-9918-77407e8b61ec)


Here it is asking for a unser name & password for the sake of the exsercies we will keep it simple and set Root for our password and user names. Thne select execute





![image](https://github.com/user-attachments/assets/a6f0bdfe-ce33-472d-b771-42f494ede237)

Next open IIS Manager as a Admin you can search for this in the start menu then right click in the IIS Manager. Select osTicket, then select new PHP manager, then select the PHP-cgi files







![image](https://github.com/user-attachments/assets/2c744605-0ba4-4233-9ad2-2585b4e59f40)

Then back in the main menu to PHP we select osTicket, and on the right side we restart the server






![image](https://github.com/user-attachments/assets/e3efac66-eb46-49fe-8550-213f06b4f392)





Next, unzip osTicket-v1.15.8. And copy and paste all of the contents from that file into C:\inetpub\wwwroot



![image](https://github.com/user-attachments/assets/6b8cf0df-475b-4d7f-a26f-556086ddee1b)

 Be sure to rename this folder to osTicket 








![image](https://github.com/user-attachments/assets/dc199fee-a10b-463b-bc30-a8496dd57718)





Next from the IIS manager menu, select osTicet > Sites > Default Web Sites > osTicekt > bwrose 




![image](https://github.com/user-attachments/assets/5068eae2-ebea-466c-9fdf-98c5c74c3ec3)









![image](https://github.com/user-attachments/assets/71968aa6-0433-4bd2-b8e0-8d2d7ce0e024)





Once in PHP manager enable the extensions I have pointed to with the arrows then refresh the server and verify the extions are enabled



![image](https://github.com/user-attachments/assets/2253f4bd-5db2-4345-b264-b556d9fa85a0)




Next go to C:> inetpub> wwwroot > osTicket> include> ost-sampleconfig.php and rename is too "ost-config.php" in the same directory 



![image](https://github.com/user-attachments/assets/322b7bef-06a7-47f0-951b-2469a06550f8)




Then right click the file and select properties in the security tab and disable inheritance , remove all exsisting permissions 




![image](https://github.com/user-attachments/assets/7d7f1343-efce-4280-b511-925467c77822)



and give everyone full access 





![image](https://github.com/user-attachments/assets/8fafd1bb-7e63-42c4-a9aa-8861dee2ef95)




Next continue with  the osTicket setup in our browser by clicking “Continue”. We assign a name of our choice to our helpdesk, and select a default email address to receive customer-submitted ticket notifications.




![image](https://github.com/user-attachments/assets/328cb5fb-56d1-4d7d-9094-f811b0ee0bdf)



Next we will install HeidiSQL once installed 









![image](https://github.com/user-attachments/assets/4e707867-417e-44a7-844a-af836f3216ee)





open it and create a new session 





![image](https://github.com/user-attachments/assets/0e8e7a00-24af-4a3a-80a2-2126f17b0d51)






It will ask for a password and user name , use root for this





![image](https://github.com/user-attachments/assets/b721c6cf-75bb-4964-a92f-45f08add31b5)





Next create a database named osTicket




![image](https://github.com/user-attachments/assets/696f5936-51d5-4884-bd8d-be2bde387391)




With your SQL database named osTicket and your user name and password as root select continue 








![image](https://github.com/user-attachments/assets/82dc5461-5b0b-4e03-92c5-cb4ddff9bab4)







Congrats, you have installed osTicke.t There are still a few things we must do inside the program, with giving certain users different abilities within the system but for now you have installed a ticket creation and resolution system! 













































  



<br />
