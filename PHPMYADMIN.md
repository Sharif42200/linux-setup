# phpmyadmin install in linux mint

## Step 1: Update Package Repository
Update the system package list to ensure you get the latest version available in the repository. Run the command below:

```
sudo apt update
```
## Step 2: Install phpMyAdmin and Apache dependencies with this command:

```
sudo apt install phpmyadmin
```
Depending on current php version **mbstring**,**curl** and **zip** needs to be installed:
```
sudo apt install php8.1-{mbstring,curl,zip,gettext}
```
```
sudo apt install php8.2-{mbstring,curl,zip,gettext}
```
```
sudo apt install php8.3-{mbstring,curl,zip,gettext}
```
The command will ask for your confirmation before installing. Type **"Y"** and press Enter to proceed.
After that the configuration file for phpmyadmin needs to copied to **/etc/apache2/sites-available/**
which is located at **/etc/phpmyadmin/apache.conf**

```
sudo cp /etc/phpmyadmin/apache.conf /etc/apache2/sites-available/phpmyadmin.conf
```
## Step 3: Check the current version of PHP:

For of all create a file named **phpinfo.php** in **/var/www/html**

```
cd /var/www/html
```

```
sudo touch phpinfo.php
```
open the following file using nano of any suitable editor with **sudo** access
```
sudo nano phpinfo.php
```
copy paste the following code
```
<?php
    phpinfo();
```

Link of the page will be [PHP Information](http://localhost/phpinfo.php).

## Step 4: Restart Apache for the changes to take effect:

```
sudo systemctl restart apache2
```

You can now access phpMyAdmin by opening a web browser and going to [PhpMyAdmin](http://localhost/phpmyadmin).
