# Install process of  Apache 

## 1. Ensure system packages are up-to-date before installation.

```
sudo apt update && sudo apt upgrade
```

## 2. Install Apache

```
sudo apt install apache2 
```
## 3. Start and Enable the Apache Service

```
sudo systemctl start apache2  

```
when the computer will open, the apache will **start automatically**.
```
sudo systemctl enable apache2
```

## 4. Verify Installation

```
sudo systemctl status apache2 
```
## 5. Access Apache Test Page

Open a web browser and navigate to http://localhost

