# wordpress
## installing Wordpress on Ubuntu 14.04

### Follow the Below commands to install wordpress on Ubuntu 14.04

sudo apt-get update

sudo apt-get install apache2

sudo apt-get install mysql-server php5-mysql

sudo apt-get install php5 libapache2-mod-php5 php5-mcrypt

sudo apt-get install php5-gd libssh2-php

mysql -u root -p
(give the password which you gave while installing)

CREATE DATABASE wordpress;

CREATE USER wordpressuser@localhost IDENTIFIED BY 'password';

GRANT ALL PRIVILEGES ON wordpress.* TO wordpressuser@localhost;

FLUSH PRIVILEGES;

exit

cd ~

wget http://wordpress.org/latest.tar.gz

tar xzvf latest.tar.gz

cd ~/wordpress

cp wp-config-sample.php wp-config.php

vi wp-config.php

```````````````````````````````````````````````````````````````````````````
// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define('DB_NAME', 'wordpress');

/** MySQL database username */
define('DB_USER', 'wordpressuser');

/** MySQL database password */
define('DB_PASSWORD', 'password');
````````````````````````````````````````````````````````````````````````````

sudo rsync -avP ~/wordpress/ /var/www/html/

cd /var/www/html

rm index.html

sudo chown -R ubuntu:www-data *

cd

mkdir /var/www/html/wp-content/uploads

sudo chown -R :www-data /var/www/html/wp-content/uploads

sudo service apache2 restart

visit the site in the IP

[http://server_domain_name_or_IP]




