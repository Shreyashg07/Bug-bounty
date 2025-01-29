# SCANING TARGETS FOR OPEN PORTS 

**SCANING TARGETS**
For possible IP address with open ports and more domains from those IP addresses.

http/https: for hosting website
ftp: file transfer 
ssh: secure communication
telnet: unsecure communication
dns : domain name mapping 

Total no ports : 65535 

OPEN METASPLOITABLE 2:

username : msfadmin
password : msfadmin 

- check ip address
```bash
ifconfig
```

- ping ip in kali for reach
```bash
ping {ip}
```

- use normal nmap command it shows open ports
```bash
nmap {ip}
```

NOTE - CHECK NMAP CHEAT SHEET IN REPO

- version listing
```bash
nmap {ip} -sV
```

If you find old version . You can exploit it . Try to search on google that any exploit available or not . Second method you can search it in kali
```bash
searchsploit version
``` 
#MOTIVE
1. Collect as many IP addresses of a target.
2. Do a port scan.
3. Do a reverse DNS.
4. Find some juice info/bug

What dns works ? <BR>
It finds the ip address.

Reverse dns : We can get domains from ip .

website : Hurricane electric - To find ASN no. <br>
open shodan type filer - asn:{ASNNO} http.status:200


#BRUTEFORCE ATTACK <BR>
<br>
OPEN BURPSUITE -> CAPTURE THE LOGIN REQUEST -> SEND IT TO INTRUDER -> TURN OFF INTERCEPT -> INTRUDER -> POSITIONS -> CHANE ATTACK TYPE:CLUSTER BOMB -> WHERE U WANT TO SELECT PAYLOAD ADD THE POINTER USING $ADD OPTION -> payload option -> add list in load option -> payload 1= username -> payload 2= password -> start attack 

**Website based ASN NO**
Hurricane Electric Services - tool for finding asn number. just type the domain name 

By asn no u can find cidr ranges and networks blocks 

**Website based cidr ranges**
ASNLOOKUP - graphical tool for cidr ranges <br>
MXToolbox - graphical tool for cidr ranges / ip addresses 


**Automated Tool based cidr ranges**
---
### *ASNMAP* <br>
---
1. Install using go .
2. run command 
```bash
asnmap -a {Any asn no} > targetcidr.txt
```

**Website based cidr ranges to ip address**

search cidr ranges to ip address to find the cidr ranges.

**Automated Tool based cidr ranges to ip address**
---
### *MAPCIDR* <br>
---
1. Install using go command.
```bash
go install -v github.com/projectdiscovery/mapcidr/cmd/mapcidr@latest
```
2. use help commad
```bash
mapcidr -h 
```
3. finding ips
```bash
mapcidr -cidr targetcidr.txt 
```
4. finding on specipic range as well as counting command
```bash
mapcidr -cidr range -c 
```

5. Output file
```bash
mapcidr -cidr range -o outputip.txt  
```

---
**Application based  ip address scanning**
---
### *ANGRY IP SCANNER* <br>

Open app > Browse > select outputip.txt > click open > click start to scan the ip .

---
**Automated Tool based cidr ranges to Domain names**
---
### *DNSX* <br>
---
1. install using Go
```bash
go install -v github.com/projectdiscovery/dnsx/cmd/dnsx@latest
``` 
2. command to find domains using cidr ranges 
```bash
echo range | mapcidr -silent | dnsx -ptr -resp-only 
```

---
**Automated Tool To find open/active ports**
---
### *naabu* <br>
---
1. install using go
2. command for help
```bash
naabu -h
```
3. To find  default  ports on domain name 
```bash
naabu -host apple.com
```
4. To find top ports
```bash
naabu -host apple.com -tp 1000
```
5. For list of ip address
```bash
naabu -l outputip.txt 
```
6. For list of ip address
```bash
naabu -p 80,443
```
7. advanced scan 
```bash
naabu -l targetip.txt -rate 3000 -retries 1 -warm-up-time 0 -c 50 -top-ports full -v 
```

--- 
### *massscan* <br>
---
This tool is used to scan any ip , port .

1. install using go
2. run command 
```bash
massscan -p 80,443 range --rate
```
3. port range
```bash
massscan -p0-1023 range --rate
```
--- 
### *rustscan* <br>
---
1. install using git clone
2. go in its directory
3. use command to scan 
```bash
rustscan -a targetip.txt -u 10000 
```
---
To check the ip details use following command
```bash
whois {ip_address}
```
---
TASK:
- collect all ports .
- Run service version detection via nmap
- Try to get access to that port / service and endpoint it .
---
### THANK YOU 