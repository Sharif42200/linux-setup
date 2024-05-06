# To install ** PHP ** on a Linux system, you can follow these general steps.

## 1. Update Package Lists:
### Before installing any new software, it's good practice to update your package lists to ensure you're getting the latest versions.
```
sudo apt update  
```

## 2. Install PHP:
```
sudo apt install php
```

## 3. If you need additional modules, you can specify them, such as:
```
sudo apt install php php-mysql php-curl php-gd php-mbstring php-xml
```

## 4. Verify Installation:
```
php -v
```
This command should display the installed PHP version.
