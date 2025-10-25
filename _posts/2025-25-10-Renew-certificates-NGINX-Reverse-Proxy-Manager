---
layout: post
title: "Nginx Revers proxy Manager - Renew certificate"
date: 2025-10-25
--- 

## See Certifcate (let's Encrypt)
```bash
sudo certbot certificates
```

and you will see the certificate name/ serial Number/domains and most important Expiry Date.

##Renew certificate 

###Case 1 Application exposed to the internet 

```bash
sudo certbot renew 
```

it will renew all the certificates you have.

###Case 2 Local application 
 
####Step 1 

you must change the record DNS type A from your local ip to your public ip

Example : 
<table>
<tr>erp.galaceram.com</tr>
</table>

