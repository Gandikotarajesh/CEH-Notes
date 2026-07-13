### Linux to Windows
#### Python
```bash
python3 -m http.server

GO to Windows -> browsers
ip:8000
```
#### /var/www/html/share
```bash
mkdir /var/www/html/share
chmod -R 755 /var/www/html/share
chown -R www-data:www-data /var/www/html/share
cp file.txt /var/www/html/share/
service apache2 start
http://<Linux-IP>/share/file.txt
```
#### Online Filetransfer
```bash
filetransfer.io
```
#### Certutil
```bash
# Linux Machine
sudo python3 -m http.server 80

# Windows Machine
Certutil.exe -Urlcache -f http://172.20.10.10/Ceh.jpg C:\path\to\save\file\Ceh.jpg
```
### Windows to Linux
#### SMB
```bash
parrot -> places -> browse network -> smb://<ip of windows> -> enter password
```
#### Python
```bash
# Windows
open cmd
python -m http.server 8000
# Linux
http://<Windows-IP>:8000/Ceh.jpg
or
wget http://<Windows-IP>:8000/Ceh.jpg
```
#### Netcat
```bash
# Windows
nc.exe <Linux-IP> 4444 < file.exe (send)

# Linux
nc -lvnp 4444 > file.exe
```

