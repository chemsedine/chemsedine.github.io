---
layout: post
title: " Renew Certificate - Nginx Reverse Proxy Manager - Certbot"
date: 2025-10-25
--- 

## See Certifcate (let's Encrypt)

Type in bash

```bash
sudo certbot certificates
```

You will see all the certificates name/ serial Number/domains and most important Expiry Date.

## Renew certificate 

### Case 1 Application exposed to the internet 

When you install certbot and generate a certificate it will automatically renew certificate.
In case it didn't you can type this command :

```bash
sudo certbot renew 
```

it will renew all the certificates you have.

### Case 2 Local application 
 
#### Step 1 
you must change the record DNS type A from your local ip to your public ip

#### Step 2
Port forward port 80 and 443 to to your local ip (where nginx is installed). <br>
Check open ports -<a href="https://www.yougetsignal.com/tools/open-ports/">here</a>-

### Step 3 
Check if DNS Record is changed using the ping command 
```bash
ping domainename.com
"ping domainename.com (your public ip) 56 bytes of data"
```
### Final step 
```bash
sudo certbot renew 
```
