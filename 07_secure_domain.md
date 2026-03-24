### Install Cerbot
```
sudo apt install certbot python3-certbot-nginx -y
```
### Secure Domain
```
sudo certbot --nginx -d domain.com -d www.domain.com
```
