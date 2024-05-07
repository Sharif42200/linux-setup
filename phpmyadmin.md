# phpmyadmin install in linux mint

## Step 1: Update Package Repository
Update the system package list to ensure you get the latest version available in the repository. Run the command below:

```
sudo apt update
```
## Step 2: Install phpMyAdmin and Apache dependencies with this command:

```
sudo apt install phpmyadmin apache2-mbencoding php-mbstring php-gettext
```
The command will ask for your confirmation before installing. Type **"Y"** and press Enter to proceed.

After the installation is finished, you'll need to configure phpMyAdmin. A configuration file will be created at ***/etc/phpmyadmin/apache.conf.*** You can edit this file with a text editor like nano to adjust settings if needed, but for basic use, the default configuration should work fine.

## Step 3: Restart Apache for the changes to take effect:

```
sudo systemctl restart apache2
```

You can now access phpMyAdmin by opening a web browser and going to "http://localhost/phpmyadmin".