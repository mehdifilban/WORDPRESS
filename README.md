# WORDPRESS
installing WordPress on Linux 
<pre>
$ wget -c http://wordpress.org/latest.tar.gz <br>
$ tar -xzvf latest.tar.gz
$ sudo rsync -av wordpress/* /var/www/html/
$ sudo chown -R www-data:www-data /var/www/html/
$ sudo chmod -R 755 /var/www/html/
$ mysql -u root -p 
mysql> CREATE DATABASE wp_myblog;
mysql> GRANT ALL PRIVILEGES ON wp_myblog.* TO 'your_username_here'@'localhost' IDENTIFIED BY 'your_chosen_password_here';
mysql> FLUSH PRIVILEGES;
mysql> EXIT;
</pre>

#### Go the /var/www/html/ directory and rename existing wp-config-sample.php to wp-config.php:

<pre>
$ sudo mv wp-config-sample.php wp-config.php
</pre>

#### then update it with your database information under the MySQL settings section (refer to the highlighted boxes in the image below):

<pre>
  gedit wp-config.php
</pre>

#### and write your information
###NOTE: The Database Collate type. Don't change this if in doubt.

#### Afterwards, restart the web server and mysql service using the commands below:
<pre>
  $ sudo systemctl restart apache2.service 
  $ sudo systemctl restart mysql.service 
</pre>

#### Open your web browser, then enter your server address: http://server-address to get the welcome page below. Read through the page and click on “Let’s go!” to proceed further and fill all requested on screen information .

#### run : <pre> localhost/wp-admin/install.php </pre>
