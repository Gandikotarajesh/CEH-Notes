#### For Hashing
```bash
hashses.com
crackstation
```
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

show result
john --show hash.txt
```
#### Hashcat
```bash
hash-identifier or hashid <hash>
apt install hashid
hashcat -m 0 hash.txt /usr/share/wordlists/rockyou.txt
hashcat -m 0 hash.txt --show
MD5 -> 0
SHA1 -> 100
SHA256 -> 1400
SHA512 -> 1700
NTLM -> 1000
bcrypt ($2a$, $2b$) -> 3200
MD5crypt ($1$) -> 500
SHA-512crypt ($6$) -> 1800
MD4 -> 900

```
#### Decrypt with VaraCrypt
```bash
Select and choose the option to mount it.
Enter the decrypted password prompted by VeraCrypt.
Once mounted, navigate to Retrieve the Secret Code within the mounted VeraCrypt volume. open and extract the secret code contained within. 
```
