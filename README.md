### wp-demo

-install and start apache2

>sudo apt-get update && sudo apt-get install -y apache2 apache2-utils mysql-client
>sudo systemctl enable apache2
>sudo systemctl start apache2

-install php modules for apache

>sudo apt-get install -y php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd

-enable rewrite module

>sudo a2enmod rewrite
>sudo service apache2 restart

-get latest wordpress version

>cd ~/ && wget http://wordpress.org/latest.tar.gz
>tar xzvf latest.tar.gz
>mv wordpress/ /var/www/
>cd /var/www/wordpress/ && mkdir wp-content/uploads
-get wp-config.php from private repo or create from sample

-change the directory owner to apache2-user

>sudo chown -R www-data:www-data /var/www/wordpress

-create config for apache-server

>cd /etc/apache2/sites-available/
-get sitename.conf from private repo or create (https://github.com/OlegStefaniuk/wp-demo/blob/master/wordpress.conf)
>cd ../sites-enabled/ && sudo ln -s ../sites-available/wordpress.conf .
