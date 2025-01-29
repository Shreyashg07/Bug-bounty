# ADVANCED NMAP FOR BUG BOUNTY 

Nmap is used to scan ip / domains / cidr ranges / ip ranges <br>
Port scan<br>
- To find which services are running on the port 
- Which services are vulnerable and old .
- Can we exploit those services ??
if yes - valid bug / if not - move to other target.

---
1. Select active target .
2. open shodan as well as cheatsheet.
3. use hostname filter 
```bash 
hostname:bsf.com
```
4. Check the suspicious ip in kali linux 
```bash
whois {ip}
```
5. Go to TOP ports more option for applying the filters .
6. use http.title 
as filter
7. scan any ip for service detection 
```bash
nmap {ip} -sV -T4 -A -min-rate 1000 -max-retries 3
```
### NMAP SCRIPTING ENGINE

run http-vuln script
```bash
nmap {ip} -t4 --script "http-vuln*"
```
run only http 
```bash
nmap {ip} --script "http*" -vv
```
check who is ip
```bash
nmap {ip} --script who-is-ip -vv
```
---

**Automated tool for scanning** 
--- 
### *Sandmap* <br>
---
1. install using git clone
2. go to directory .
```bash 
cd sandmap
```
3. check the directory
```bash 
ls
```
4. run the file 
```bash 
./setup.sh 
```
5. use commands step by step
```bash
help
show port scan
use port scan
show 
set destination {targetip}
init 4
init 0
main
list 
use service detection 
set destination {ip}
init 1
```
--- 
### *SCANCANNON* <br>
---
1. install using git clone
2. go to directory
```bash
cd scancannon/
```
3. put cidr ranges in cidr.txt
4. Run the tool
```bash
./scancannon.sh cidr.txt
```

--- 
Solve the room of NMAP : TRY HACKME
---
### THANK YOU 