#### Login Bruteforce
```bash
Burpsuite -> Proxy -> Open Browser
enter random username and password
turn on intercept before clicking on login
request captured in Burpsuite
right click-> send to intruder
-> turon off intercept
clear
select admin -> add $
select pass -> add $

select attack type -> cluster bomb
go to payload section
anter the usernames and passwords in the two payloads
Start attack
validate length

```
