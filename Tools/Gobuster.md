```bash
gobuster dir -u <url> -w <wordlist>

Gobuster dir -u http:// -w wordlist -e .html, .css, .js, .conf

file extensions
gobuster dir -u http://<TARGET_IP>/ -w /usr/share/wordlists/dirb/common.txt -x php,asp,aspx,jsp,bak,old,zip,txt,log,ini
```
#### Find .txt file
```bash
gobuster dir -u http://training.cehorg.com -w /usr/share/seclists/Discovery/Web-Content/common.txt -x txt
```
#### FFUF
```bash
ffuf -u http://www.abc.com/FUZZ -w /<>/
```
