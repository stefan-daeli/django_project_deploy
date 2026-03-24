### Sites Available
```
cd /etc/nginx/sites-available/
```
```
sudo nano project_name.conf
```
```
server {
    server_name domain.com www.domain.com 00.00.00.000;

    location = /favicon.ico {
       alias /var/www/projects_directory/project_name/static/img/favicon.ico;
       access_log off;
    }
    location /static/ {
        alias /var/www/projects_directory/project_name/staticfiles/;
    }

    location /media/ {
        alias /var/www/projects_directory/project_name/media/;
    }

    location / {
        include proxy_params;
        proxy_pass http://unix:/run/project_name_gunicorn.sock;
    }
}
```
### Sites Enabled
```
cd /etc/nginx/sites-enabled/
```
```
ln -s /etc/nginx/sites-available/project_name.conf /etc/nginx/sites-enabled/
```
```
nginx -t
```
### Start Nginx
```
systemctl daemon-reload
```
```
systemctl restart nginx
```
```
systemctl status nginx
```
