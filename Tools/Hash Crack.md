#### John the ripper
```bash
john --wordlist=/usr/share/wordlists/rockyou.txt user2
john user2 --show

john --format=raw-md5 --wordlist=/usr/share/wordlists/rockyou.txt 
```
#### Hashact
```bash
hashcat -m 0 -a 0 hash.txt /usr/share/wordlists/rockyou.txt
```
