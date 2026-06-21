#### Tools Usage
```bash
Snow, stegsnow     --> TXT
Steghide --> .jpg/ .jpeg / .bmp
zsteg    --> PNG
binwalk  --> Any
exiftool --> Metadata
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
steghide extract -sf MyTrip.jpg -p Password
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

