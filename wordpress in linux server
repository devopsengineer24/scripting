#!/bin/bash  
sudo apt-get update
sudo apt-get install apache2
sudo apt-get install mysql-server 
sudo add-apt-repository ppa:ondrej/php 
sudo apt-get install php7.3 
sudo apt install php7.3-cli php7.3-fpm php7.3-json php7.3-pdo php7.3-mysql php7.3-zip php7.3-gd php7.3-mbstring php7.3-curl php7.3-xml php7.3-bcmath php7.3-json 
sudo mysql_secure_installation
sudo mysql << QUERY_INPUT
create database bitnami_wordpress; 
CREATE USER 'bn_wordpress'@'localhost' IDENTIFIED BY '45bee7e8ac'; 
GRANT ALL ON bitnami_wordpress.* TO 'bn_wordpress'@'localhost' IDENTIFIED BY '45bee7e8ac'; 
SELECT DISTINCT User FROM mysql.user; 
FLUSH PRIVILEGES; 
EXIT;
QUERY_INPUT
cd /var/www/html/
sudo  wget -c http://wordpress.org/latest.tar.gz 
sudo tar -xzvf latest.tar.gz 
sudo rm -rf latest.tar.gz
sudo chown -R www-data:www-data /var/www/html/
sudo service apache2 restart
echo "Installation is complete."
