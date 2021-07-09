# google-cloud


https://www.youtube.com/watch?v=vIJdypOqlL4

https://www.youtube.com/watch?v=QUYCiIkzZlA

https://www.youtube.com/watch?v=46Ic_XTb_wo

https://www.youtube.com/watch?v=eXtqqofrhOo

https://www.youtube.com/watch?v=BLzbqAIyVwc

https://www.youtube.com/watch?v=a2g9pDleGQk

https://pythonise.com/series/learning-flask/deploy-a-flask-app-nginx-uwsgi-virtual-machine

https://uwsgi-docs.readthedocs.io/en/latest/WSGIquickstart.html

https://www.techatbloomberg.com/blog/configuring-uwsgi-production-deployment/

https://uwsgi-docs.readthedocs.io/en/latest/ThingsToKnow.html

https://www.youtube.com/watch?v=p6R1h2Nn468

https://www.youtube.com/watch?v=K7g4D4sdBEQ

```   
  git clone https://github.com/shahinur198/covid_unit.git
   cd covid_unit/
   mv covid_care_web.zip ..
   cd ..
   sudo rm -r covid_unit/
   sudo apt-get install unzip
   unzip covid_care_web.zip
   sudo rm -r covid_care_web.zip
   ls
   16  mv covid_care_web/ app
   17  ls
   18  cd ~/app
   19  ls
   20  python -m venv env
   21  ls
   22  source env/bin/activate
   23  pip install --upgrade pip
   24  pip install -r requirements.txt
   25  pip list
   26  sudo ufw status
   28  sudo ufw enable
   29  sudo ufw allow 9090
   30  sudo ufw status
   
   31  uwsgi dev.ini 
   32  sudo ufw delete allow 9090
   33  sudo ufw status
   34  deactivate
#........................................................................
   35  sudo apt install nginx
   36  sudo ufw app list
   37  sudo ufw allow 'Nginx HTTP'
   sudo ufw allow 'Nginx HTTPS'
   38  sudo ufw status
   39  sudo systemctl status nginx
   40  sudo nano /etc/systemd/system/app.service

   [Unit]
Description=A simple Flask uWSGI application
After=network.target
[Service]
User=dailycarebscow
Group=www-data
WorkingDirectory=/home/dailycarebscow/app
Environment="PATH=/home/dailycarebscow/app/env/bin"
ExecStart=/home/dailycarebscow/app/env/bin/uwsgi --ini app.ini
[Install]
WantedBy=multi-user.target

   41  sudo systemctl start app
   42  sudo systemctl enable app
   43  sudo systemctl status app
   44  sudo nano /etc/nginx/sites-available/app

   server {
    listen 80;
    server_name 34.136.135.47;
    location / {
        include uwsgi_params;
        uwsgi_pass unix:/home/dailycarebscow/app/app.sock;
    }
}

   45  sudo nginx -t
   46  sudo ln -s /etc/nginx/sites-available/app /etc/nginx/site
s-enabled/
   47  sudo nginx -t
   48  sudo systemctl restart nginx
   49  history
   Every time you pull any changes from your remote repo, you'll need to restart the app service with:

sudo systemctl restart app
If you make any changes to the Nginx sites-enabled file, you'll need to restart Nginx with:

sudo systemctl restart nginx
```

https://vlemon.com/BLOG/Google-Cloud-Platform/install-ssl-certificate-on-nginx-web-server-on-ubuntu
SSL certificate Settings
```
sudo apt-get update
sudo apt-get install software-properties-common
sudo add-apt-repository ppa:certbot/certbot
sudo apt-get update
sudo apt-get install python-certbot-nginx 

sudo certbot --nginx

sudo certbot renew --dry-run
```
https://www.youtube.com/watch?v=QUp9XYL7E5o

https://vlemon.com/BLOG/Google-Cloud-Platform/install-ssl-certificate-on-nginx-web-server-on-ubuntu

https://www.youtube.com/watch?v=245ZJLm1AV4

https://www.youtube.com/watch?v=2yaq-0C-cmU

https://www.youtube.com/watch?v=sTDVsMUegL8
