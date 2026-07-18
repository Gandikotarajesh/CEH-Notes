#### TO find the elf files and entropy value
```bash
for file in *.elf; do echo "File: $file"; ent "$file" | grep Entropy; echo; done

sha348sum <filenameWithHighEntropy> 

```
