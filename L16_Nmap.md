# Nmap For Bug Bounty Part 1 

host discovery - arp response scan using disable port scan.

```bash
nmap -PR -Sn {ip}
```

Port scan
```bash
nmap -PR {ip} -p80 --reason
```
### Arp requests 
sender ---> reciver<br>
reciver <---- sender

### ICMP Host discovery { not fiseable because most of firewalls block it}

```bash
nmap -PE -Sn {ip} --reason
```


### 3 WAY HANDSHAKE

client ---SYN---> server<br>
client <---SYN/ACK--- server<br>
client ---ACK---> server<br>

### States of port
1. open - service available.
2. close - no service.
3. filter - nmap donot know port is open or close due to firewall .
4. unfilter - port is accessible but nmap donot know .
5. open/filter - nmap donot have any idea .
6. closed / filter - nmap donot have any idea .
---
### TCP Host discovery

synchronization
```bash
nmap -PS -Sn {ip} --reason
```

acknowlegement
```bash
nmap -PA -Sn {ip} --reason
```
check the arp response on live target 

```bash
nmap -iL targetip.txt -PR -sn
```
host up / down requests 
```bash 
nmap -iL targetip.txt -PR -sn -vv 
```
OR 
```bash
massscan -iL targetip.txt -rate 5000 -P80,443
```
scan on the livedomains which has no http prefix 
```bash 
nmap -iL livedomains.txt -Sn -PR 
```
 Service version detection
```bash
nmap {ip} -sV -T5 -Pn -vv
```
---
### THANK YOU 