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

