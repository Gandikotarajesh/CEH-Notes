#### Python
```bash
python3 -m http.server

GO to Windows -> browsers
ip:8000
```
#### Certutil
```bash
Certutil.exe -Urlcache -f http://<ParrotIP>/eg.jpg C:\path\to\save\file\eg.jpg
```
```bash
wget http://<Windows_IP>:8080/eg.jpg -O eg.jpg
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
