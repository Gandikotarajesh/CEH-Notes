#### Tools Usage
```bash
Snow     --> TXT
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

