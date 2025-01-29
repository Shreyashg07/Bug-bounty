# Finding XSS Automated and Manual Way Part 2 


1. Choose event handler payloads 
2. Insert that payload everywhere possible 
3. Read the source page 
4. Try to execute the payload or try to bypass the filters or mitigation.


### Encoder the payloads 

**website based**
1. encoder decoder
2. base64

### Seclist payloads 
1. Search seclist on github
2. Go to fuzzing folder
3. Go to xss section 
4. Copy all payloads to one file .

### Burpsuite 
1. setup proxy and visit the website
2. turn on intercept
3. Add request to scope .use filter to show only scope.
4. Right click and click spidering host. Go to spider option
5. click on pararmeters to check the different parameters .
6. Select any parameter url and send it to intruder.
7. Write any thing in querry / parameter value add the position.
8. Go to payload option browse the copy payload files .
9. click start attack 
---

**AUTOMATED TOOL**
--- 
### *katana* <br>
---

1. Install using go.
2. use help command
```bash 
katana -h 
```
3. Gather all parameter urls
```bash
katana -u example.com 
```

--- 
### *waybackurl* <br>
---

1. Install using go.
2. use chatgpt 

---
### THANK YOU 
