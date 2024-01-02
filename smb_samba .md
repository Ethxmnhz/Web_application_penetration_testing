```┌──(kali㉿kali)-[~]
└─$ nmap 10.10.33.65 -sV -p 22,139,445 -sC
Starting Nmap 7.94SVN ( https://nmap.org ) at 2024-01-02 15:13 IST
Nmap scan report for 10.10.33.65
Host is up (0.38s latency).                                                                                                                                                                                                                 
                                                                                                                                                                                                                                            
PORT    STATE SERVICE     VERSION                                                                                                                                                                                                           
22/tcp  open  ssh         OpenSSH 7.2p2 Ubuntu 4ubuntu2.10 (Ubuntu Linux; protocol 2.0)                                                                                                                                                     
| ssh-hostkey:                                                                                                                                                                                                                              
|   2048 10:8a:f5:72:d7:f9:7e:14:a5:c5:4f:9e:97:8b:3d:58 (RSA)                                                                                                                                                                              
|   256 7f:10:f5:57:41:3c:71:db:b5:5b:db:75:c9:76:30:5c (ECDSA)
|_  256 6b:4c:23:50:6f:36:00:7c:a6:7c:11:73:c1:a8:60:0c (ED25519)
139/tcp open  netbios-ssn Samba smbd 3.X - 4.X (workgroup: WORKGROUP)
445/tcp open  netbios-ssn Samba smbd 4.3.11-Ubuntu (workgroup: WORKGROUP)
Service Info: Host: TECHSUPPORT; OS: Linux; CPE: cpe:/o:linux:linux_kernel

Host script results:
| smb-os-discovery: 
|   OS: Windows 6.1 (Samba 4.3.11-Ubuntu)
|   Computer name: techsupport
|   NetBIOS computer name: TECHSUPPORT\x00
|   Domain name: \x00
|   FQDN: techsupport
|_  System time: 2024-01-02T15:14:16+05:30
| smb2-security-mode: 
|   3:1:1: 
|_    Message signing enabled but not required
|_clock-skew: mean: -1h49m56s, deviation: 3h10m29s, median: 2s
| smb2-time: 
|   date: 2024-01-02T09:44:17
|_  start_date: N/A
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 29.25 seconds
```


i use nmap scripts for enumerating shares and i found out some share and i try to connect with smbclient 

```
┌──(kali㉿kali)-[~]
└─$ smbclient //10.10.33.65/websvr
Password for [WORKGROUP\kali]:
Try "help" to get a list of possible commands.
smb: \> ls
  .                                   D        0  Sat May 29 12:47:38 2021
  ..                                  D        0  Sat May 29 12:33:47 2021
  enter.txt                           N      273  Sat May 29 12:47:38 2021

                8460484 blocks of size 1024. 5700016 blocks available
smb: \> 
```


