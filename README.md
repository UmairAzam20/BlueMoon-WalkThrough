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

```bash
nmap -sn 192.168.100.0/24
```
So we get several IP Address but the one i we need is the MAC Address that set in our VM.
which we get this:




