# BlueMoon-WalkThrough
BlueMoon: 2021 - A boot2root CTF challenge from VulnHub (Easy difficulty). Goal: Get root access and capture all flags.

## Machine Details:

Release date: April 7, 2021 

Author: Kirthik 

Difficulty: Easy 

Goal: Get root! (find all 3 flags) 

Open ports: 21 (FTP), 22 (SSH), 80 (HTTP) 

Key techniques: Directory brute-forcing, QR code decoding, Hydra password cracking, sudo misconfiguration, Docker group privilege escalation 

## Phase 1: Reconnaissance

1. Network Discovery
   
```bash
nmap -sn 192.168.100.0/24
```
So we get several IP Address but the one we need is the MAC Address that set in our VM.
which we get this:

![Nmap Scan Results](screenshot/IpAddressBlueMoon.png)

 2. Port Scanning
Scan for open ports and services:

```bash
nmap -sV -sC -Pn -vv 192.168.100.117
```

Results :

Port	Service	Version

21/tcp	FTP	vsftpd 3.0.3

22/tcp	SSH	OpenSSH 7.9p1

80/tcp	HTTP	Apache httpd 2.4.38

## Phase 2: Enumeration 
Visit the web server on port 80. Nothing useful on the main page or source code.

Directory Brute-forcing :

```bash
gobuster dir -u http://192.168.100.117 -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-medium.txt -x ,php,.html,.bak
```
Discovered directory: /hidden_text

![Nmap Scan Results](screenshot/enumeration.png)




