```bash
python3 /opt/john/ssh2john.py key.txt > dekey.txt
#This to transfer the ssh key to type can john the ripper understand it.

jonh --wordlist=/usr/share/wordlists/rouckyou.txt dekey.txt
#This used to crack password
```
