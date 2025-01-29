# XSS/Cross Site Scripting Vulnerability

To execute Javascript codes on web applications with an intention to execute those without proper input validation by the web applications.

alert(1) or prompt("Shreyash") <br>
Javascript Language <br>
HTML Language <br>

```bash
<script> alert("shreyash")</script>
```
 --> put in search bar of test.php


---
### HOW TO FIND THE XSS ? 
1. At any search form or input form .<br>
(1) - Intention : alert(1) <br>
(2) - Modification : Modify the code .
2. Hunt for xss on different parameters .

testphp.vulnweb.com/comment.php?aid=2

aid = parameter <br>
2 = value

---
### TYPES OF XSS 
1. Reflected xss : popular - search bar 
2. Stored xss : popular - Login page
3. DOM xss : Least
4. Blind xss : mid popular 

- Escape from textarea
```bash
</textarea><script>alert("Hello")</script>
```

- Escape from inner HTML input
```bash
document.getElementsByClassName('name')[0]innerHTML='Defronix';
```

Task :
1. solve Try hack me xss room.
2. solve xss lab on port swigger. 

---
### THANK YOU 