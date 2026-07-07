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

### Windows to Linux
#### SMB
```bash
parrot -> places -> browse network -> smb://<ip of windows> -> enter password
```
