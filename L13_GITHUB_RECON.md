# GITHUB RECON AND SENSITIVE DATA EXPOSURE 

**GITHUB RECON**
1. Automated : Different tools arer used.
2. Manual : Human approach - best 
---
**MANUAL WAY **

Search using github-dorks
check all dorks 
eg. *****google.com**** * password use this in the search bar of github.

To remove test crendentials use :
eg: * google.com * Password NOT test NOT example 

TIP : best encoder / decoder tool : crack station / base64
---
**AUTOMATED WAY**
1. GITDORKER 
- install using git clone
- go to directory
```bash
cd GitDocker
```
- install requirements
```bash
pip3 install -r requirements.txt 
```
OR 
```bash
apt install python3-termcolor
apt install python3-tqmd
apt install python3-requests
```
OR
- set path
```bash
python3 -m env venvpath
```
- activate
```bash
source venvpath/bin/activate
```
- now install
```bash
pip3 install -r requirements.txt 
```
---
- go to dorks
```bash
cd dorks
```
- run recon
```bash
python3 Gitdorker.py -d dork/mediumdorkers.txt -tf tf/TOKENSFILE -q google.com -lb 
```

---

Configure token 
```bash
cd tf/
```

```bash
ls
```

```bash
cat Tokenfile
```

```bash
vim TOKENSFILE
```

```bash
paste token
```
---
Tasks :
1. Choose target
2. Do manual github recon to find secrets 
3. Use tools like gitdorker or gitgraber

OTHER TOOLS LIKE THIS : Trufflehog , gitgraber