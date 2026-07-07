#### DVWA setup
```bash
$ docker
$ sudo apt install docker.io
$ sudo systemctl enable docker
$ sudo systemctl start docker
$ sudo systemctl status docker
$ sudo docker run hello-world (check docker is running)
```
#### DVWA
```bash
docker pull citizenstig/dvwa
# run
docker run -d -p 80:80 citizenstig/dvwa
# install
http://127.0.0.1/dvwa/index.php
```
#### Owasp juice shop
```bash
docker pull bkimminich/juice-shop

# run
docker run --rm -p 3000:3000 bkimminich/juice-shop
# Install
http://localhost:3000/
```
#### bwapp
```bash
docker pull hackersploit/bwapp-docker
# run
docker run -d -p 80:80 hackersploit/bwapp-docker
# Install
http://127.0.0.1/install.php
```
#### Commands
```bash
sudo docker images
docker run --rm -p 3000:3000 bkimminich/juice-shop
http://localhost:3000
ctrl+c to close
 if u get error while starting again
docker ps
docker stop <container id>
```

#### Links
```bash
# DVWA
https://hub.docker.com/r/citizenstig/dvwa

# Owasp Juice Shop
https://hub.docker.com/r/bkimminich/juice-shop

# bwapp
https://hub.docker.com/r/hackersploit/bwapp-docker
```
