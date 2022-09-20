# AWS EC2
## Taking Domain
## Creating Machine
## Elastic IP
## Bitwise
## nginx Setup 
Follow https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04  
In Step 2 execute the following ones!
```bash
sudo ufw allow 'OpenSSH'
sudo ufw allow 'Nginx Full'
```
> *sudo ufw allow 'OpenSSH' is so critical, if not allowed the machine won't be reachable ever again!*
After nginx is installed, please change ownership of *www* folder by
```bash
sudo chown ubuntu www
```
Then go inside it and create a seperate folder for your website.
## SSH Certificate
Follow https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04