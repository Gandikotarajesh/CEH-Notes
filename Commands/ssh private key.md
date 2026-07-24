```bash
copy id_rase and save as key.txt in local machine
python3 /opt/john/ssh2john.py key.txt > dekey.txt
#This to transfer the ssh key to type can john the ripper understand it.

jonh --wordlist=/usr/share/wordlists/rouckyou.txt dekey.txt
#This used to crack password
here we will get passphrase

# Login as user kay
cd /home/kay/.ssh
ssh -i id_rsa kay@10.48.149.227
Enter the passphrase

Now if you are already logged in as a another user
Cd /home/kay/.ssh/id_rsa kay@ip
Enter passphrase:

#errors check
find / -name ssh2john.py 2>/dev/null
then if find work on this path
or
check python version
```
#### Method 2
```bash
save as id_rsa in local machine
chmod  600 id_rsa
ssh root@ip -i id_rsa
if any error
ssh root@ip -p 50706 -i id_rsa
```
