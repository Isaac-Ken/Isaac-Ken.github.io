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



**ENUMURATION**
---
