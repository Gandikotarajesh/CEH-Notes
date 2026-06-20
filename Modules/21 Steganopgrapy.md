#### Tools Usage
```bash
TXT -> Snow
JPG -> Steghide
PNG -> zsteg
Any -> binwalk
Metadata -> exiftool

#### File type check
file file name

#### SNOW (.txt)
Snow -C -p password file.txt

#### Steghide (.jpg/ .jpeg / .bmp)
Steghide extract -sf image.jpg

#### Binwalk (Any file to check hidden files)
Binwalk image.jpg
Binwalk -e img.jpg

#### Zsteg( .png)
Zsteg image.png

#### Exiftool (Metadata)
Exiftool image.jpg
```

