# PostgreSQL Command Documentation

## 1. Switch to PostgreSQL User and Open psql:

```
sudo -u postgres psql
```
* Purpose: Log in as the **postgres** user to access the PostgreSQL command-line interface (psql).

* Prerequisite: Requires superuser privileges to switch users.

## 2. Change Password for the postgres User:

```
ALTER USER postgres PASSWORD '123456';
```
* Purpose: Update the password for the **postgres** user to **123456**.

* Note: Replace **123456** with a secure password.

## 3. Create a New Database:

```
CREATE DATABASE name;
```
* Purpose: Creates a new database named name.
* Usage: Replace name with the desired database name.

## 4. Import Data from a SQL File:

```
sudo psql -h localhost -d test_msx1080 -U postgres < /home/pc-1/Share/test_msx1080.sql
```
* Purpose: Import the SQL dump file test_msx1080.sql into the test_msx1080 database.

* Options:
    * -h localhost: Connect to the local database server.
    * -d test_msx1080: Specify the target database.
    * -U postgres: Use the postgres user to connect.
    * <: Redirect input from the specified file.

## 5. Export a Database to a SQL Dump File:

```
pg_dump -h postgrestest02.c9og5810afad.us-east-1.rds.amazonaws.com -U postgres -p 5438 -d test_msx1080 > test_msx1080.sql
```
* Purpose: Create a backup of the test_msx1080 database as a SQL dump file named test_msx1080.sql.

* Options:
    * -h: Hostname of the remote PostgreSQL server.
    * -U postgres: Username for the database connection.
    * -p 5438: Port number for the PostgreSQL server.
    * -d test_msx1080: Specify the database to export.
    * . >: Redirect output to the specified file.

