#### Expert Info Analasys
```bash
Wireshark -> Analyse -> Expert Information
```
#### Filter with Subnet
```bash
ip.addr == 192.168.1.0/24
```
#### Quick notes
```bash
- To find number of packets associated with IP → `statics -> filter by IPv4--> Source and Destination ---> Then you can apply the filter`
    - Eg: For highest no.of packets sent `tcp.flags.syn == 1 and tcp.flags.ack == 0` or filter my given `IP`
- Filter with Frame Content → `frame contains "string"`
- For Expert information `Analyse -> Expert Info`
- IoT Publish Message use `mqtt` filter
- Dos detection
    - Open connections
        - `tcp.flags.syn == 1 && tcp.flag.ack ==0`
        - `tcp.flags.syn == 1`
    - `Statistics → Conversations`, if no. of packets targeted on one IP from different source address and no reply back, it indicates DDoS
    - Detection with Graphs (`Statistics → I/O Graph Menu`) [ if there is a spike in overall packets then its a sus ]
```
#### TO find passwords
```bash
http.request.method == POST
check HTTP requests


Password Sniffing using Wireshark- In pcap file apply filter: http.request.method==POST (you will get all the post request)
Now to capture password click on edit in menu bar, then near Find packet section, on the "display filter" select "string",
also select "Packet details" from the drop down of "Packet list", also change "narrow & wide" to "Narrow UTF-8 & ASCII", and then type "pwd" in the find section.
```
#### IOT
```bash
# IoT Publish Message
Search for "IOT Publish Message" 
Edit → find packet →  select packet Details  Search for the string or  use frame.contains "IoT Publish Message

# Filter with mqqt
```
#### Basic ip Filter
```bash
# ip.addr == 10.10.10.9

# Filter by dest ip
ip.dst == 10.10.10.15

# Filter by source ip
ip.src == 10.10.16.33

# Filter by tcp port
tcp.port == 25

# Filter by ip addr and port
ip.addr == 10.10.14.22 and tcp.port == 8080

# Filter SYN flag
tcp.flags.syn == 1 and tcp.flags.ack ==0

# Broadcast filter
eth.dst == ff:ff:ff:ff:ff:ff
```
####  Filter HTTP requests
```bash
http.request 
```
####  Filter DNS queries 
```bash
dns.qry.name 
```
#### DDoS attack launched against a target at 172.22.10.10
```bash
"Statistics" > "IPv4 Statistics" > Source and destination Addresses > Type ip.dst == 172.22.10.10 (In Display Filter)
or
Go to statistics IPv4 addresses--> Source and Destination ---> Then you can apply the filter given 
tcp.flags.syn == 1 and tcp.flags.ack == 0

-------------------
Go to statistics IPv4 addresses--> Source and Destination ---> Then you can apply the filter given 
tcp.flags.syn == 1 and tcp.flags.ack == 0  
you can find the high number of packets send to10.10.1.10 address and that answer.
----------------
```

####  DDoS attack launched against a target at 10.10.1.10
```bash
 Go to statics → converstaoins
 click IPv4 tab
In Address A(attacker: find the highest packet count here) and B(victim: 10.10.1.10) columns 
```
#### IOT packet containing the "High_temperature"
```bash
mqtt && frame contains "High_tempurature"
```

