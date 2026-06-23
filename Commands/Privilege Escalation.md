#### check for privileges
```bash
sudo -l
```
#### Login as another User
```bash
sudo -u user2 /bin/bash
```
#### Using SSH private key
```bash
nano id_rsa
chmod 600 id_rsa
ssh root@<ip> -p 50706 -i id_rsa
```
