# awesome
a python web app based on awesome-python-webapp by michaelliao
# How to install
sudo yum install nginx gunicorn  supervisor mysql-server python-gevent

  (后面这个python-gevent本来应该放到pip中安装，但安装经常出错，所以用YUM安装反倒成功）

sudo pip install mysql-connector jinja2

启动MYSQL并设置ROOT的密码,下例中密码为root

sudo service mysqld start

mysqladmin -u root password 'root'

sudo cp conf/nginx/awesome /etc/nginx/

sudo cp conf/supervisor/

