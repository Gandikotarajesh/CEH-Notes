#### Linux
```bash
find / -type f -name Netnormal.txt 2> /dev/null
sudo find / -name *.txt
sudo find / -name SpecificFileName.txt
sudo find /DirecrotyName -name SpecificFileName.txt
sudo find . -name SpecificFileName.txt

# with Username
find / -type f -user elyana 2>/dev/null
```
#### Windows
```bash
dir \webpent.txt /s /b
tree → Both Linux and Windows.
dir “sa_code* /s /b”
```
#### Contents in windows
```bash
type flag.txt
```
#### Locate tool
```bash
locate tool
sudo apt update 
sudo apt install mlocate -y 
sudo updatedb

Or
apt-get install locate -y
sudo updatedb
```

#### Optional
```bash
• find . -name flag1.txt: find the file named “flag1.txt” in the current directory
• find /home -name flag1.txt: find the file names “flag1.txt” in the /home directory
• find / -type d -name config: find the directory named config under “/”
• find / -type f -perm 0777: find files with the 777 permissions (files readable, writable, and executable by all users)
• find / -perm a=x: find executable files
• find /home -user frank: find all files for user “frank” under “/home”
• find / -mtime 10: find files that were modified in the last 10 days
• find / -atime 10: find files that were accessed in the last 10 day
• find / -cmin -60: find files changed within the last hour (60 minutes)
• find / -amin -60: find files accesses within the last hour (60 minutes)
find / -size 50M: find files with a 50 MB size
```
