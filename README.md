# rino-system-d

/home/pi/rino/release/configuration/web_page

> run_backend.sh 
python3 /home/pi/rino-frontend-api/general_code/tempRINO/run.py

> run_frontend.sh
#!/bin/bash
cd ~/rino-frontend && serve -s build

> rino-backend.service
> rino-frontend.service

[Unit]
Description=RINO WEB FrontEnd
After=network.target

[Service]
User=pi
ExecStart=/bin/bash /home/pi/rino/release/configuration/new_webpage/run_frontend.sh start
Restart=always
RestartSec=60

[Install]
WantedBy=multi-user.target
```
$ sudo mv Desktop/rino-backend.service /etc/systemd/system
$ sudo mv Desktop/rino-frontend.service /etc/systemd/system
```
```
$ sudo service rino-backend restart
$ watch -n2 sudo service rino-backend status
```
How to enable services
`$ sudo systemctl enable rino-backend.service`

```
$ journalctl -fu rino-backend.service
$ journalctl -ru rino-backend.service 
```

