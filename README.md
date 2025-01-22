
This project demonstrates the setup of a fully functional web server environment using Red Hat Linux as the operating system. The Apache web server is configured to serve web content, while MariaDB is used for database management. For programming, PHP is integrated to create dynamic, server-side applications. 

A sample login webpage is created to showcase the server's capabilities.


## Installation

Install Apache web server, MariaDB and PHP

```bash
sudo dnf install httpd mariadb-server php php-mysqlnd -y

systemctl start httpd && systemctl enable httpd && systemctl status httpd

systemctl start mariadb && systemctl enable mariadb && systemctl status mariadb
```
Secure the Database Installation

```bash
mysql_secure_installation
```
Create a php info page
```bash
echo "<?php phpinfo(); ?>" | sudo tee /var/www/html/info.php
```
Open browser and navigate to http://<your__IP>/info.php.

You can see the PHP information page.

![php info page](https://github.com/user-attachments/assets/d45e1c0b-2cb4-4c4e-91e4-8fbe68751641)

Now lets create a login page.

You can write your own code or check my index.php file for code

```bash
cd /var/www/html/

vim index.php
```

After completing the index.php file restart httpd (apache) web server

```bash
systemctl restart httpd
```

Open browser and navigate to http://<your__IP>

![login page](https://github.com/user-attachments/assets/aa4273d9-e13b-488a-b0cf-6dd42ec457e8)
