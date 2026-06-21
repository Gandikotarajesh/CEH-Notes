#### Hide.cfe decrypt
```bash
use CryptoForge tool (windows)
```
#### file is base 64
```bash
Linux
cat file.txt | base64 -d

-d -> decrypt

Windows
we can use cyberchef
or
Get-Content filename.txt | ForEach-Object { [System.Text.Encoding]::UTF8.GetS 
tring([System.Convert]::FromBase64String($_)) }
```
#### encryption, decryption, encoding, decoding and hashing
```bash
Cyberchef (windows)
```
#### John The Ripper
```bash
Identiy the hash
hashid <hash>
OR
hash-identifier

Crack MD5
john --format=Raw-MD5 --wordlist=rockyou.txt hash.txt
```
#### Decrypt with VaraCrypt
```bash
Select and choose the option to mount it.
Enter the decrypted password prompted by VeraCrypt.
Once mounted, navigate to Retrieve the Secret Code within the mounted VeraCrypt volume. open and extract the secret code contained within. 
```
