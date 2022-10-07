
*Title*

**RECON**
---
**PRTG Network Monitor**  

![recon](https://user-images.githubusercontent.com/66635295/186772798-f68057b0-5c42-4ded-a665-79e936d7b05b.png)

**Nmap Scan**  

<pre>nmap -sC -sV 10.10.10.152</pre>  

Anonymous FTP login allowed

![nmap](https://user-images.githubusercontent.com/66635295/186772901-4dbe931e-e585-4aad-918d-24040a0d7fc6.png)

**ENUMURATION**
---
**FTP**

<pre>ftp 10.10.10.152</pre>

![ftp](https://user-images.githubusercontent.com/66635295/186773102-ae133107-e0b4-4246-a72d-2a29a57f3841.png)

**User Flag**
---

<pre>ls</pre>

<pre>cd Users/Public</pre>

<pre>get user.txt</pre>

![userflag](https://user-images.githubusercontent.com/66635295/186773291-fe1c48a2-5581-4659-b4e6-783acd531408.png)

**Privilege Escalation**
---
Looking through Config files

![prtg](https://user-images.githubusercontent.com/66635295/189782263-e5bb9bee-6c29-4abc-aa49-794107ad7f82.png)

User and password in PRTG Configuration.old.bak

![loginu](https://user-images.githubusercontent.com/66635295/189796463-7db0c558-9173-41a0-b85b-f05af5839faa.png)


Log into Netmon using 2019 for updated crenditals (box release year)

![welcome](https://user-images.githubusercontent.com/66635295/189796496-5bf4bcf9-d5ea-4d81-968b-c0a2979af4ed.png)


**Root Flag** 
---

Looking for PRTG Network Monitor vulnearbilies 

![cve](https://user-images.githubusercontent.com/66635295/189796533-62636b8d-14bf-4f00-ae0c-54a9c8ad44dd.png)


Blog post about exploitation method

![walkthrough](https://user-images.githubusercontent.com/66635295/189796555-343d76fc-fa0a-4c9d-9d79-718c2a5df6bf.png)


Add Notification: Setup > Account Settings > Notifications

![add noti](https://user-images.githubusercontent.com/66635295/194221916-c1bbf595-481b-4dba-a2b3-cd24447de267.png)
 
 Powershell to transfer
 
 ![copyitem](https://user-images.githubusercontent.com/66635295/194221942-42df0ec0-b6f1-4494-a742-ccd6d6bd0ddc.png)
 
Formating transfer
![e x](https://user-images.githubusercontent.com/66635295/194221962-3ddbb65a-e261-462b-ac27-6e69135a1a9d.png)

Anonymous FTP succesfull transfer 

![root](https://user-images.githubusercontent.com/66635295/194221976-86fbc050-579f-4c64-bd4b-2bde7bc649d5.png)



 
