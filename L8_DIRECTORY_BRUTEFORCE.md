# DIRECTORY BRUTE FORCE

It is used to access the 404 error page using various extension like .php ,.js etc.

**SUBDOMAIN ENUMERATION TOOL** 
1. ONE FOR ALL - {chinese tool}
- install from github
```bash
git clone
```
- help slide
```bash
python3 oneforall.py -h 
```
- enumeration command 
```bash
python3 oneforall.py --target samsung.com
```

### SCHEDULING
1. Subfinder
2. ffuf 
3. oneforall
4. screenshoting
6. Dir bruteforce 

**DIRECTORY BRUTEFORCE TOOLS**
1. FFUF 
- already installed in subdomain enumeration 
- command to run
```bash
ffuf -w /usr/share/sirb/wordlist/big.txt -u url -mc 200
```

2. Dirsearch
- install
```bash
apt install dirsearch
```
- command to run the recon
```bash
dirsearch -l target.txt -e php,asp,aspx,html -i 200,404
```
 

---

### THANK YOU 
