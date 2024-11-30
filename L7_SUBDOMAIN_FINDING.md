# SUBDOMAINS ENUMERATION

1. Finding as many as subdomains we can
2. Remove the duplicates entry 
3. Sort out the live subdomains 
4. screenshot 

**Website based information gathering**

- crt.sh : 
[crt.sh](https://crt.sh/)

- Virus Total :
[Virus_Total](https://www.virustotal.com/gui/home/upload)

- NET CRAFT
[NET_CRAFT](https://www.netcraft.com/)

- Chaos
[Chaos](https://chaos.projectdiscovery.io/)


**Automated Tool based information gathering**
---
### *SUBFINDER* <br>
---
2 methods of installing 

1. install using go lang
```bash
go install -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder@latest
```

2. Add the Go bin path to the system paths. On OSX or Linux, in your terminal use
```bash
echo export PATH=$PATH:$HOME/go/bin >> $home/.bashrc
source $home/.bashrc
```

3. The binary will be located in $home/go/bin/subfinder

4. Usage
```bash
subfinder -h 
```

> OR

1. Install using zip file . Go to [Release_page](https://github.com/projectdiscovery/subfinder/releases)

2. use Wget command after copying the amd64 link for linux machine .
```bash
Wget https://github.com/projectdiscovery/subfinder/releases/download/v2.6.7/subfinder_2.6.7_linux_amd64.zip
```

3. Unzip the file
```bash
unzip subfinder_2.6.7_linux_amd64.zip
```

4. Locate the path
```bash 
sudo mv subfinder /usr/local/bin/
```

5. Create a configuration directory 
```bash
mkdir -p ~/.config/subfinder
```

6. Go to subfinder directory
```bash
cd .config/subfinder/
```

7. Run subfinder listing command to add files in subfinder/ 
```bash
subfinder -ls
```

8. Add the api keys in the file
```bash
open providerprovider-config.yaml
```

9. Run the final command  for information gathering
```bash
sunfinder -d  example.com -o target.txt -v
```

---
### *AMASS* <br>
---
1. Install amass
```bash
apt install amass
```

2. Download both files from github and paste it in the  amass directory [config.yaml](https://github.com/owasp-amass/amass/blob/master/examples/config.yaml) &  [datasource.yaml](https://github.com/owasp-amass/amass/blob/master/examples/datasources.yaml)

3. Run the command using 
```bash
amass enum -passive -d example.com -o target.txt
```

---
### *CHAOS-CLIENT* <br>
---

1. INSTALL CHAOS CLIENT 
```bash 
go install -v github.com/projectdiscovery/chaos-client/cmd/chaos@latest
```

2. Ensure that change the directory
```bash
sudo mv $HOME/go/bin/chaos /usr/local/bin/
```

3. Export the chaos key 
```bash
export CHAOS_API_KEY="your-chaos-api-key"
```

4. Run the tool
```bash
chaos -d example.com -o target.txt -v
```

---
### *FFUF* <br>
---

This tool gives you the active subdomains using its wordlists.

1. Install using go 
```bash
go install github.com/ffuf/ffuf@latest
```

2. verify using 
```bash
ffuf -h
```

3. Download the worldlist from the url [nokova_subdomains]( https://raw.githubusercontent.com/n0kovo/n0kovo_subdomains/main/n0kovo_subdomains_large.txt
)
```bash
wget https://raw.githubusercontent.com/n0kovo/n0kovo_subdomains/main/n0kovo_subdomains_large.txt
```

4. Run the command using 
```bash
ffuf -w n0kovo_subdomains_large.txt -u https://FUZZ.example.com -v -of csv -o output.csv
```

5. Clean the CSV Output to Extract Valid URLs
```bash
awk -F',' '{print $1}' output.csv > cleaned_urls.txt
```

6. Remove duplicates :
```bash
awk -F',' '{print $1}' output.csv | sort | uniq > cleaned_urls.txt
```

7. clean urls by removing http:/https:/
```bash
sed 's/^https\?:\/\///' cleaned_urls.txt > final_cleaned_urls.txt
```

---

**SORTING AND REMOVING DUPLICATES**

---
### *HTTPX-TOOLKIT* <br>
---

1. Install 
```bash
apt install httpx-toolkit
```

2. verify working
```bash
httpx-toolkit -h 
```

3. run the tool
```bash
cat target.txt | httpx-toolkit > targetfinal.txt 
```

4. check the count 
```bash
cat targetfinal.txt | wc -l
```

---

**SCREENSHOOTING**

---

---
### *EYEWITNESS* <br>
---
1. Installation
```bash
apt install eyewitness
```

2. Run command using timeout as the default timeout is 7.
```bash 
eyewitness -f targetfinal.txt --web --timeout 120
```
---

### THANK YOU 