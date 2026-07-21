#### Quick notes
```bash
# use this command if there is any RAT related
 nmap -Pn -n -p 6703, 9871 10.10.55.0/24
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

 nmap -Pn -p 6703 ip/24 
# Process
-> Navigate to E:\CEH-Tools\CEHv12 Module 07 Malware Threats\Trojans Types\Remote Access Trojans (RAT)\Theef and double-click Client210.exe to access the victim machine remotely.
-> Enter the IP address of the target machine in the IP field, and leave the Port and FTP fields set to default; click Connect.
-> Click on File explorer icon > File manager > Expand Hard 
Drive C: > Users folder > Martin Folder > and find Scan folder > count file present in Scan folder > Enter it as answer.
```
#### NjRat
```bash
Execute NjRat
Insert IP and Port
Click on manager and open directory
```
#### Tips
```bash
Scan all ports with nmap (-p-). Look for the unknown ports. Use theef RAT to connect to it. 
2. main ports check 9871,6703 
3. nmap -p 9871,6703 192.168.0.0/24 
4. now you get open port ip address 
5. now go to the c drive malware/trojans/rat/theef and run the client.exe file 
6. now entry the ip of open port and click connect and click on file explorer and find the sa_code.txt. 
7. or search file in cmd using command --→ dir /b/s “sa_code*” it shows the path.
```
