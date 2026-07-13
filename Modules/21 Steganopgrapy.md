#### Tools Usage
```bash
Snow, stegsnow     --> TXT
Steghide --> .jpg/ .jpeg / .bmp
zsteg    --> PNG
binwalk  --> Any
exiftool --> Metadata
Convert TCP --> For hiding data in TCP/IP packet header
Openstego --> jpg
Snow --> Hiding and extracting data from a text file.

# GUI
OpenStego -> png/bmp
```

#### File type check
```bash
file file name
```
#### SNOW (.txt)
```bash
Snow -C -p password file.txt
```
#### Steghide (.jpg/ .jpeg / .bmp)
```bash
Steghide extract -sf image.jpg

with Password
steghide extract -sf image.jpg -p Password

# Additional detal

which steghide
sudo apt install steghide -y
which steghide
man steghide

# Embeding data
steghide embed -cf regular_image.jpeg -ef super_secret_stuff.txt

# Extract data from Image
steghide extract -sf regular_image.jpeg -P <PASS>

```
#### Binwalk (Any file to check hidden files)
```bash
Binwalk image.jpg
Binwalk -e img.jpg
```
#### Zsteg( .png)
```bash
Zsteg image.png
```
#### Exiftool (Metadata)
```bash
Exiftool image.jpg
```

#### Stegsnow (extract hidden data from file)
```bash
stegsnow -p password -C restricted.txt output.txt 
```

### Windows
#### OpenStego
```bash
open it > choose Extract data > select image file Ceh.jpg > select folder to save extracted file > Click on extract data.
```
#### SNOW
```bash
SNOW.EXE -C -p "pass" hidden.txt

```
