#### Quick notes
```bash
# use this command if there is any RAT related
 nmap -Pn -n -p 6703 10.10.55.0/24
```
#### List Of Tools
```bash
njRAT
MoSucker
ProRat (require password)
Theef (no pass)
HTTP RAT 
```
#### Quick notes
```bash
- To access RAT → `Theef → Client210.exe` Tool (to get target IP, look for Target with `ports 9871, 6703` open)
- To find Entry points, Linker info → `PEiD tool`
- To find Entropy values
    - `DIE` → Windows (Can also be used to find segment sizes with different hashes)
    - `ent` → Linux
- Address of Entry or Entry point Address → `PE Explorer`
    - Entry Points → `DIE → PE` and cross check with `PEiD` (linker info)
```
#### Ports
```bash
Theef default port: 9871, 6703, FTP 2968
NJRAT default port: 5552
MoSucker default port: 200005
ProRat default port: 5110
```
#### ProRat
```bash
Execute ProRat
Set victim IP and relative port 5110
Click to connect and search files.
```
#### Theef
```bash
Execute Theef
Set victim IP and relative ports to 9871, 6703 and 2968 (or custom port)
Click to connect and open file manger.
```
#### NjRat
```bash
Execute NjRat
Insert IP and Port
Click on manager and open directory
```
