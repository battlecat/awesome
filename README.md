# awesome
a python web app based on awesome-python-webapp by michaelliao
# How to install
sudo yum install nginx mysql-server gcc

  (后面原来是准备安装这个python-gevent，但用YUM安装显示成功但是无法调用命令。
  
  后来放到pip中安装，但安装经常出错，看问题后是缺少gcc导致的。
  
  用yum安装gcc，再用pip安装gevent成功。）

sudo pip install mysql-connector jinja2 gunicorn  supervisor gevent

启动MYSQL并设置ROOT的密码,下例中密码为root

sudo service mysqld start

mysqladmin -u root password 'root'

导入数据库SQL文件

sudo mysql -u root -p < schema.sql

复制配置文件到相应目录

sudo cp -f conf/nginx.conf /etc/nginx/nginx.conf

sudo cp -f conf/supervisord.conf /etc/supervisord.conf

重启supervisor

supervisorctl reload

supervisorctl start awesome

用status查看

[ec2-user@ip-172-31-18-152 awesome]$ supervisorctl status

awesome                          RUNNING   pid 12591, uptime 0:00:30

可以用ps -efH|grep python查看运行的进程中有它

启动nginx成功
 
 sudo /etc/init.d/nginx start

无法显示前端，如果

sudo python wsgiapp.py
