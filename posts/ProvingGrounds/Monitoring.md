*Monitoring*

**RECON**

---
**Ip Search** 
Investigating the IP shows Nagios XI  
![image1](https://user-images.githubusercontent.com/66635295/158923291-f9f3c79d-29cd-4356-abac-a06c8a23c1c8.png)
**Login Page** 
![image4](https://user-images.githubusercontent.com/66635295/158923386-5a962c6b-12a7-4478-8ac3-7a4a7dbbfb76.png)



**Nmap Scan**  
<pre>nmap -sC -sV -A 192.168.54.136 </pre>  
-safe scripts -service version -OS /version detection  
![image3](https://user-images.githubusercontent.com/66635295/158923500-63ccf817-750b-4cc0-b922-5fec2ac9aed3.png)

**Exploit Search**
<pre>msfconsole </pre>   
<pre>search nagios </pre>   
![image7](https://user-images.githubusercontent.com/66635295/158925208-7aaf44af-6018-45f6-9136-02605a2546df.png)

**Service Version**
Provided Exploits Did not work howeve rreavel the service version   
![image6](https://user-images.githubusercontent.com/66635295/158925523-9ec073a8-fad8-47e2-a719-fd456de16bdd.png)  
**Google-Fu**
<pre>Nagios XI Remote Code Execution</pre> 
Exploit allows for root access prior to 5.6.6  
![image11](https://user-images.githubusercontent.com/66635295/158925803-ec6d2456-8095-4b7c-9e4b-b1cbced68f63.png)

**ENUMURATION**
---
**Exploit**
<pre>use exploit /linux/http/nagios_xi_autheticated_rce</pre>
Reveales it had been moved  
![image8](https://user-images.githubusercontent.com/66635295/158925989-31db1f9c-15ac-4db7-91c5-ec38690de593.png)


**Privilege Escalation**
---
  
**User Flag**      
  

**Root Escalation**
---  
**Root Flag**  
 
