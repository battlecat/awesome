# awesome
a python web app based on awesome-python-webapp by michaelliao
# How to install
sudo yum install nginx mysql-server python-gevent

  (后面这个python-gevent本来应该放到pip中安装，但安装经常出错，所以用YUM安装反倒成功）

sudo pip install mysql-connector jinja2 gunicorn  supervisor

启动MYSQL并设置ROOT的密码,下例中密码为root

sudo service mysqld start

mysqladmin -u root password 'root'

导入数据库SQL文件

sudo mysql -u root -p < schema.sql

复制配置文件到相应目录

sudo cp -f conf/nginx/nginx.conf /etc/nginx/nginx.conf

sudo cp -f conf/supervisor/supervisord.conf /etc/supervisord.conf

启动supervisor

supervisord -c /etc/supervisord.conf




 sudo supervisorctl stop awesome
 
 sudo supervisorctl start awesome
 
 sudo /etc/init.d/nginx reload

