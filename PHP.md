# To install **PHP** on a Linux system, you can follow these general steps.

## 1. Update Package Lists:
### Before installing any new software, it's good practice to update your package lists to ensure you're getting the latest versions.
```
sudo apt update && apt upgrade
```
Once all the packages are installed, add this PPA using the following command:

```
sudo add-apt-repository ppa:ondrej/php
```
```
sudo apt-get update
```

## 2. Install PHP:
```
sudo apt-get install php8.1
```
```
sudo apt-get install php8.2
```
```
sudo apt-get install php8.3
```

## 3. If you need additional modules, you can specify them, such as:
```
sudo apt install php8.1-{mysql,gd,mbstring,xml,zip,fileinfo,mbstring}
```

```
sudo apt install php8.2-{mysql,gd,mbstring,xml,zip,fileinfo,mbstring}
```

```
sudo apt install php8.3-{mysql,gd,mbstring,xml,zip,fileinfo,mbstring}
```

## 4. Verify Installation:
```
php -v
```
This command should display the installed PHP version.



## 4. Change the current PHP version:
To check the available **PHP** modules the following command can be used:
```
sudo update-alternatives --list php
```
To Change the **PHP** version following command can be used(**This will change the local PHP version not for apache**):
```
sudo update-alternatives --config php
```
To Change the version for **apache2** first currently active version needs to be disabled:

```
sudo a2dismod php8.1
```

Then desired **PHP** version needs to be enabled:
```
sudo a2enmod phpp8.3
```
 After that **apache2** needs to be restarted:
 ```
 sudo systemctl restart apache2
 ```
