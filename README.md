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
```
