### Gunicorn Socket
```
sudo nano etc/systemd/system/project_name_gunicorn.socket
```
```
[Unit]
Description=django project gunicorn socket

[Socket]
ListenStream=/run/project_name_gunicorn.sock

[Install]
WantedBy=sockets.target
```
### Gunicorn Service
```
sudo nano /etc/systemd/system/gunicorn.service
```
```
[Unit]
Description=gunicorn daemon
Requires=django_project_gunicorn.socket
After=network.target

[Service]
User=root
Group=www-data
WorkingDirectory=/var/www/projects_directory/project_name
ExecStart=/var/www/projects_directory/project_name/venv/bin/gunicorn \
          --access-logfile - \
          --workers 3 \
          --bind unix:/run/gunicorn.sock \
          config.wsgi:application

[Install]
WantedBy=multi-user.target
```
### Start Gunicorn
```
sudo systemctl daemon-reload
```
```
sudo systemctl start gunicorn.socket
```
```
sudo systemctl enable gunicorn.socket
```
```
systemctl status gunicorn.socket
```
