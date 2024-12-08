# DUBDOMAIN TAKEOVER

Domain can use any cloud service 

- Cname- canonical name - map one domain to another with any ip address 

Cloudflare -DNS service manager

EG.
CNAME 
help.defronix.com  defronix.github.io TTL

Github Repository : Defronix_rep-cloud service Host-Defronix.github.io

**THEORY/CONCEPT**
After 5 years i don't need this Defronix Repo cloud service What i will do ? I will delete this repo/ service 
But i forget to remove that CNAME entry from my dns record.
A hacker when find  this subdomain {help.defronix.com} from recon/subdomain enumeration when ghe will visit this subdomains he will get 404 error page by github (defronix.github.io)
The hacker will try to takeover subdomain by creating same subdomain at that cloud servuce provider and uploading a simple index.html file.

STEPS :
1- Create a html file.
2- Upload on github page
3- Go to setting -> pages -> source (deploy from branch)-> select folder (/root)

**GITHUB REPO TO IDENTIFY THE VULN CLOUD SERVICE**

> Can-i-take-over

**CHECK CNAME RECORD**
1. Using dig command
```bash
Dig subdomain CNAME
```
2. Using nslookup
```bash
nslookup subdomain
```

**TOOLS TO FIND SUBDOMAIN FOR TAKEOVER**

1. SUBJACK
- Install 
```bash
go install github.com/haccer/subjack@latest
```
- Set up path 
```bash
export PATH=$PATH:$(go env GOPATH)/bin
```
- install the tool
```bash
apt install subjack
```
- run the tool
```bash
subjack -h
```
- Run the command to find the severity 
```bash
subjack -w subdomains.txt -t 100 -o results.txt -v 
```
- filter the output 
```bash
sed '/\[Not Vulnerable\]/d' input.txt > output.txt
```

2. SUBZY 
- Install
```bash
git clone https://github.com/PentestPad/subzy.git
cd subzy
```
IT IS NOT WORKING ...

3. Nuclei 
- install
```bash
apt install nuclei
```
- check working 
```bash
nuclei -h
```
- Move the path 
```bash
cat /root/.zhrc -> move ./echo$Path
```
- Open nuclei github 
nuclei-templates->subdomain-takeover/detect-all-take-over.yaml
- select Raw copy link -> go to kali -> root -> local ->nuclie-templates -> create new folder {subdomain-takeovers } -> right click open terminal -> paste the command
```bash
wget url
```
- Run the recon
```bash
nuclei -l target.txt -t /root/local/nuclei-templates/subdomain-takeover -v
```
- update templates if needed or in future
```bash
nuclei -update-templates
```
- enter the folder
```bash
cd ~/.nuclei
```


**AWS SERVER TAKEOVER**
1. GO to AWS -> AWS S3 Console -> Create bucket 
2. Bucket name : any your choice 
3. ACL Disable -> Create bucket 
4. Permissions : Edit block all public access
5. Static web hosting : Enablke / index document : index.html 
save changes 
6. Redirect requests for objects 
7. Host name : help.defronix.com
8. Protocol:https
9. Upload index.html 
10. metadata/content-type/value= text/html


