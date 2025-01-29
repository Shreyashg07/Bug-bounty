# FINDING MISSCONFIGURED AWS S3 BUCKET

LOGIN AWS -> S3 SERVICE -> CREATE BUCKET -> REMOVE BLOCK ALL PUBLIC ACCESS 

**AUTOMATED TOOL**
---
### *AWSCLI* <br>
---

1. install 
```bash
apt install awscli
```
2. commands 
```bash
aws s3 ls s3://myteswtbucket9958 -no-sign-request
```
3. recon
```bash
 aws S3 cp S3://mytestbucket9958/jssecrets.txt/root/jssecrets.txt --no-sign-request
```
NOTE: ALL COMMANDS ARE NOT CHECKED SO PLS USE ANY SOURCE TO VERIFY THEM

---

### THANK YOU 