# Javascript files analysis for secret information/leakage

1. Find a target 
2. Find all possible subdomains or links from the target as well as its subdomains. 
 
## TOOLS USED - subfinder , httpx , subjs  
**Information gathering- subdomain enumeration**
```bash
subfinder -d target url -all -o example.txt -v
```
**Finding active and removing duplicates subdomains**
```bash
cat example.txt | httpx > uniq.txt
```
**Fetch javascript files from a list of URLS use TOOL - SUBJS**
- installation > search subjs on browser > open link > click on release > subjs_1.0.1_linux_amd64.tar.gz > right click and copy link address.

``` bash 
wget https://github.com/lc/subjs/releases/download/v1.0.1/subjs_1.0.1_linux_amd64.tar.gz
```

- unzip the file 

```bash 
tar -xvf subjs_1.0.1_linux_amd64.tar.gz
```

- Check path 

```bash 
echo $path 
```

- Move the file at path 

```bash 
mv subjs /usr/bin/subjs
```

- Run Tool

```bash
cat target.txt | subjs > targetsubjs.txt 
```

**KATANA TOOL SETUP AND USAGE**

- installation > search katana tool > go to github repository > and copy go cmd and paste it in your terminal 

```bash 
CGO_ENABLED=1 go install github.com/projectdiscovery/katana/cmd/katana@latest
```
---
#### *Only use if issues occurs like command not found*

- check your path 

```bash 
export PATH=$PATH:/root/go/bin
```

Now try running Katana:

```bash
katana
```

- Move the go to local bin 

```bash
echo $PATH
```

```bash
sudo mv /root/go/bin/katana /usr/local/bin/
```
Now try running Katana:

```bash
katana --help
```
---


- Fetch all urls of domain

```bash
katana -u target.com -d 5 
```

- fetch only js file 

```bash
katana -u target.com -d 5 -jc | grep ".js$"
```

- fetch js files from our txt file 

```bash 
katana -list targetuniq.txt -jc -o targetjs.txt | grep ".js$"
```

- unique urls 

```bash
sort targetjs.txt |uniq -d > targetjsuniq.txt 
```

**ANOTHER BACKUP TOOL IS GETJS**

**SECRETFINDER**

- install

```bash 
git clone https://github.com/m4ll0k/SecretFinder.git secretfinder
```

- go to directory 

```bash
cd secretfinder
```

- check for requirements

```bash 
python -m pip install -r requirements.txt or pip install -r requirements.txt
```

OR 

```bash
cat requirement.txt
```
then install requirements

- run the tool using

```bash
python3 SecretFinder.py
```

- recon using

```bash
cat targetjsuniq.txt | while read url; do python3 SecretFinder/SecretFinder.py-i $url -o cli > outputstore.txt; done
```

- sorted token list

```bash
grep -rE 'aws_access_key|aws_secret_key|api key |passwd|pwd|hero ku|slack | firebase|swagger|aws key password|ftp password|jdbc|db|sql|secret jet config|admin|json|gcp|htaccess|\.env|ssh key|. git| access key | secret token| oauth_token| oauth_token_secret' rapydsorted.txt 
```

**NUCLEI TOOL**

- Install

a. Download the Binary
```bash
curl -sSL https://github.com/projectdiscovery/nuclei/releases/latest/download/nuclei-linux-amd64.zip -o nuclei.zip 
```
b. Unzip the File
```bash
unzip nuclei.zip
```
c. Move the Binary to /usr/local/bin
```bash
sudo mv nuclei /usr/local/bin/
```
d. Verify Installation
```bash
nuclei -version
```

- RUN TOOL using

```bash
nuclei -l targetjsuniq.txt -t nuclei-templates/file/keys
```

**MANTRA Tool**

- install

```bash
go install github.com/MrEmpy/mantra@latest
```

- use 

```bash
cat targetjssorted.txt | mantra 
```
---

### THANK YOU 
