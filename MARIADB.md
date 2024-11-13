# How to Install MariaDB on Ubuntu

## Step 1: Update Package Repository
Update the system package list to ensure you get the latest version available in the repository. Run the command below:

```
sudo apt update
```
## Step 2: Install MariaDB
Install the MariaDB package by running the following command:
```
sudo apt install mariadb-server -y
```

The **-y** flag automatically answers **yes** to any prompts during the installation. You can remove the flag if you want to review the prompts.

After installation, the MariaDB service starts automatically.

## Step 3: Verify Installation
Verify that the database service is active and running. Run the following command:
```
sudo systemctl status mariadb
```

# How To Create a New User and Grant Permissions in MySQL:
### 1. Run mysql command as root:
```
sudo mysql -u root -p
```
### 2. Create a new user with root privileges and password-based authentication. Use the syntax below:
```
CREATE USER 'example-user'@'localhost' IDENTIFIED BY 'password';
```
```
GRANT ALL PRIVILEGES ON *.* TO 'example-user'@'localhost';
```
### 3. Flush the privileges to ensure they are saved:
```
FLUSH PRIVILEGES;
```
To exit the monitor and return to the terminal, run:
```
exit;
```
or
```
\q
```

### optional :: to enter in the new user you just created:
```
sudo mysql -u example-user -p
```


# How To Import a Database:

### 1. Login to MariaDB:
```
sudo mysql -u root -p
```

### 2. Create a Database:
```
CREATE DATABASE name;
```
**Here name should be name of the valid database**
**Step 2 can be skiped if datbase is already created**

### 3. Use the Database:
```
use name;
```
**Here name should be name of the valid database**

### 4. Import:
```
source path/of/sql/file.sql;
```

### 5. Disable Strict mode:
```
sudo nano /etc/mysql/my.cnf
```
### 6. append:
```
[mysqld]
sql_mode=
```

After that restart the database

```
sudo systemctl restart mysql
```

```
sudo systemctl restart mariadb
```
