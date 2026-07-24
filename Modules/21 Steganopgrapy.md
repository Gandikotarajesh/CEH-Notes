#### To see Image
```bash
xdg-open image.jpg
eog image.jpg
```
#### Tools Usage
```bash
TXT                --> Snow, stegsnow
jpg/jpeg /bmp      --> Steghide
PNG                --> zsteg   
Any                --> binwalk
Metadata           --> exiftool
jpg                --> Openstego  

# GUI
OpenStego -> png/bmp
```
#### Approach
```bash
file
strings
exiftool
binwalk
steghide
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

# Additional detail

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
#### Sample
```bash
# Run strings to see if any text is hidden
strings MyTrip.jpg | grep -E '[A-Za-z0-9]{8}'
Looks for 8-character alphanumeric string

# Try extracting hidden content with steghide
steghide extract -sf MyTrip.jpg
If asked for passphrase and not given, just press Enter

# Read the extracted file
cat steg.txt | grep -E '[A-Za-z0-9]{8}'

Alternative method
binwalk -e MyTrip.jpg
```
