*Funbox Easy*

**RECON**

---
**Ip Search**  
Apache Server  
![image14](https://user-images.githubusercontent.com/66635295/159646178-ab903bdc-44d6-4fff-88a9-23279bd1bd5f.png)

**Nmap Scan**  
<pre>nmap 192.168.54.111</pre>  
 Knowing Funbox Rookie  not really expecting much from nmap. Dirb will be better  
![image11](https://user-images.githubusercontent.com/66635295/159646241-09d9fc6b-3b51-44a0-940a-10d757d6cac2.png)  
**Dirb**
<pre> dirb http:// 192.168.54.111 </pre>
![image9](https://user-images.githubusercontent.com/66635295/159838630-52b57a84-a48a-432c-99a4-82ddb3220bbf.png)  
![image13](https://user-images.githubusercontent.com/66635295/159838668-7011e6b1-ca86-4cff-a242-8c0044220ef0.png)  


**ENUMURATION**
---
**Admin Page**
<pre> Name: admin  </pre>  
<pre> Pass: admin </pre>  
Accepts basic admin credentials   
![image10](https://user-images.githubusercontent.com/66635295/159838808-74b66b91-a7dc-491c-acf8-4bc0cb6aa74a.png)  
**Add New Book**  
Notice the image files  
![image7](https://user-images.githubusercontent.com/66635295/159838890-53cb1c83-daee-45fa-8b3f-7c5078b99618.png)

**Create New Book**  
Uploading reverse PHP Shell in images    
![image2](https://user-images.githubusercontent.com/66635295/159838930-bbbd34b1-a8e8-40ce-a369-be8aa9ba5125.png)
**Shell Exploit**  
Pentest Monkey Reverse PHP    
![image1](https://user-images.githubusercontent.com/66635295/159838982-54625cd5-df41-4deb-bbf4-c9bd33f1dccd.png)
**Configure the Shell**  
Open up a Netcat listener   
<pre>nc -lvp 8000   </pre>  
![image16](https://user-images.githubusercontent.com/66635295/159839332-0c9c90df-00e4-41ff-ad32-1d4a327d6d0a.png)

**Find shell**  
Running drib on the store page it appears to be using bootstrap. Check the img directory  
![image3](https://user-images.githubusercontent.com/66635295/159839387-0001fc05-c997-4bd5-ba0d-2f49d0503191.png)  
**Image Index**  
![image4](https://user-images.githubusercontent.com/66635295/159839421-2c411dff-652c-4ade-9399-bea19d0175dc.png)

**Privilege Escalation**
---
**Reverse Shell**
Opening the php lands a reverse shell
![image6](https://user-images.githubusercontent.com/66635295/159839585-994be4ad-5c91-44d4-8e65-a76a9c628445.png)

**User Passwords**
<pre> cd home  </pre>
<pre> cd tony  </pre>
<pre> cat password.txt  </pre>
![image15](https://user-images.githubusercontent.com/66635295/159839741-f6fd75c7-e088-475c-9034-6354deebf38a.png)


<pre>   </pre>
<pre>   </pre>
<pre>   </pre>

<pre>   </pre>
<pre>   </pre>
<pre>   </pre>
<pre>   </pre>
  

**Root Escalation**
---  
**Root Flag**  
 

