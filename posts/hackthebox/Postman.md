![postman](https://user-images.githubusercontent.com/66635295/177882324-7b24b663-8911-4c1c-81c6-85fbc14f3ea8.png)

**RECON**
---
**Unfinished Website**
![recon](https://user-images.githubusercontent.com/66635295/177882332-fd817d49-3650-4a0b-b8cf-9bd12907a41d.png)

**Nmap Scan**
<pre>nmap –p- -A -T4 10.10.10.160</pre>
-allports -version -Aggressive

Port 6379 Redis and Port 1000 Webpage
![nmap](https://user-images.githubusercontent.com/66635295/177882433-ba2d38f8-69fc-49e7-99ff-10ab7c868bd8.png)

**Webpage check**
Wepbpage shows an error, link does not work 
![10000](https://user-images.githubusercontent.com/66635295/177882646-5ebf6232-adf3-4e15-8cdd-b284ba8791f7.png)

Navigating to the proper page reveals Webmin login 
![webmin](https://user-images.githubusercontent.com/66635295/177882796-f0ff7900-9296-4471-b394-01b121af3ef9.png)

**Redis Install**
<pre> sudo apt-get install redis-tools </pre>
![redis install](https://user-images.githubusercontent.com/66635295/177883042-2adb0cbf-6e2c-44bc-a428-e99c52c57325.png)

**Redis Host**
<pre>redis-cli -h 

![redis-h](https://user-images.githubusercontent.com/66635295/178047298-847ee0b2-b196-4674-ab2e-499e5b6a23fc.png)
