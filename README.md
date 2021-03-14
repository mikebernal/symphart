# Setting up a PHP project using Apache2 server

## User friend terminal command for installing PHP, MySQL, and Apache2

``sudo apt install php libapache2-mod-php php-mysql``

To check if you install apache2 correctly, go to your web browser and open: localhhost<br/>
To check if PHP is installed in your system, go to yoru terminal and type ``php -v`` it should display the php version installed.

## Installing composer

Make sure you are in your home directory by typing in terminal ``cd ~`` then download the installer using this curl command <br/> ``curl -sS https://getcomposer.org/installer -o composer-setup.php``<br/>

To install composer globally type in the terminal again <br/> ``sudo php composer-setup.php --install-dir=/usr/local/bin --filename=composer
``<br/>

To test if composer is installed in your system, open a new terminal and type composer. A list of composer commands should display in your terminal.<br/>

## Requirements:

1. PHP
2. Database?
3. Apache2 
4. PHPMyAdmin?
5. Composer

## Steps

1. Create your local project inside your root directory ~/project_name ``mkdir project_name``
2. Setup your PHP project_name using composer ``cd project_name`` AND ``composer init``
3. Create your index file ``touch index.php``
4. Write a test input ``nano index.php`` AND type inside``<?php echo "Hello world"; ``
5. Save the file by pressing CTRL + X THEN Y and press return
6. Add your project_name to your hosts file ``sudo nano /etc/hosts`` AND type ``127.0.0.1 project_name.local`` 
7. Save changes by pressing CTRL + X THEN Y and press return
8. Copy 000-default.conf using <br/> ``sudo cp /etc/apache2/sites-enabled/000-default.conf /etc/apache2/sites-enabled/project_name.conf``
9. Replace the /etc/apache2/sites-enabled/project_name.conf content into this:
![config](vhost.png)

Change the symphart to your project_name

10. Save the changes by pressing CTRL + X THEN choose Y and return
11. Edit your apache2.conf and add your local project directory and settings ``sudo nano /etc/apache2/apache2.conf`` AND
add these lines. <br/>
![apache2.conf](apache2.conf.png)
<br> Change the symphart and use your own project_name.
    
12. Restart apache2 just to make sure everything is working by ``sudo systemctl reload apache2``
13. Go to your web browser and go to your local project host url you have configured in your /etc/hosts file like symphart.local
14. If everything goes well, you should see a screen like this: <br />
![Itworks](hello-world.png)

in your case, it's Hello world!
    
