## Notes on web setup.    
    
Acquire domain name.    
    
> https://713527d4-9feb-4015-be1d-6d3dd68b0e89.org    
    
Setup minimal ubuntu machine.    
    
> ssh root@164.92.164.44    
> adduser paulduchesne    
> usermod -aG sudo paulduchesne    
> rsync --archive --chown=paulduchesne:paulduchesne ~/.ssh /home/paulduchesne    
> ssh paulduchesne@164.92.164.44    
    
Install nginx and certificates.    
    
> sudo apt update    
> sudo apt install -y nginx    
> systemctl status nginx    
    
> sudo snap install --classic certbot    
> sudo ln -s /snap/bin/certbot /usr/bin/certbot    
> certbot certonly --nginx --noninteractive --agree-tos --email paulduchesne@tuta.io -d 713527d4-9feb-4015-be1d-6d3dd68b0e89.org    
    
Replace nginx.conf    
    
> service nginx restart    
