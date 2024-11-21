# Implementing a Client Server Architecture using MySQL Database Management System (DBMS).

Implementing a Client-Server Architecture using MySQL Database Management System (DBMS) involves setting up a system where the client (front-end application or user interface) communicates with a server (back-end service) that manages the database operations using MySQL DBMS.

**To demonstrate a basic client-server using MySQL RDBMS, follow the below instructions**

## Create and configure two Linux-based virtual servers (EC2 instances in AWS).

    Server A name - mysql server
    Server B name - mysql client

## On mysql server Linux Server install MySQL Server software.

    1. **Update your package index:** Before installing MySQL, it's a good practice to update your system's package list to ensure you have the latest package information.

       sudo apt update

![update](./Image/sudo%20apt%20update.png)

2.  **Install MySQL Server:** Install the MySQL Server package by running the following command:

            sudo apt install mysql-server

![install_myqsl_server](./Image/install%20mysql.png)

3.  **Secure MySQL Installation:** After installation, run the mysql_secure_installation script to secure your MySQL installation. This will help you set up a root password and configure other security settings.

        sudo mysql_secure_installation

Note: You will be prompted to do the following as done in project 1

- Set a root password (if not already set).
- Remove insecure default settings (e.g., test database, remote root login).
- Reload privilege tables.

![secure](./Image/secure%20installation.png)

4.  **Check MySQL Status:** After installation, you can check if MySQL is running with:

        sudo systemctl status mysql

![status](./Image/mysql%20status.png)

5.  Access MySQL Command Line: To access the MySQL shell, use the following command:

           sudo mysql -u root -p

    _Note: Enter your root password when prompted._

6.  In the Inbound rules, open a new TCP port 3306 with the client public ip address/32

![inbound_rules](./Image/updated%20inbound%20rules.png)

7.  **Allow remote access**:

- Open the MySQL configuration file:

        sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf

- Change the bind-address to your server's public IP address or 0.0.0.0 to allow connections from all IPs:

        bind-address = 0.0.0.0

![bind_address](./Image/bind%20address.png)

- Save the file and restart MySQL

        sudo systemctl restart mysql

8.  Access MySQL Command Line:

           sudo mysql -u root -p

**Enter the password when prompted**

9.  Create MySQL Users and Databases: You can create new users and databases within MySQL to begin managing your data:

        CREATE DATABASE mydatabase;
        CREATE USER 'myuser'@'%' IDENTIFIED BY 'mypassword';
        GRANT ALL PRIVILEGES ON mydatabase.* TO 'myuser'@'%';
        FLUSH PRIVILEGES;

## On mysql client Linux Server install MySQL client software.

1.  **Update the Package Index:** Before installing, ensure your system's package list is up-to-date:

        sudo apt update

![update](./Image/sudo%20apt%20update%20client.png)

2.  Install MySQL Client: Use the following command to install the MySQL client package:

        sudo apt install mysql-client

![install_client](./Image/install%20mysql%20client.png)

## From mysql client Linux Server connect remotely to mysql server Database Engine withoutusing SSH. You must use the mysql utility to perform this action.

- **Syntax to Connect to the MySQL Server:** The basic syntax to connect to a MySQL server is:

         mysql -u [username] -p -h [hostname or IP] -P [port]

- -u [username]: The MySQL username to log in as.
- -p: Prompts for the user's password.
- -h [hostname or IP]: The hostname or IP address of the MySQL server. Use localhost if connecting to the local server.
- -P [port]: Specifies the port (default is 3306).
  mysql -u root -p -h 16.170.146.206 -P 3306

_Enter the password when prompted to_

## Check that you have successfully connected to a remote MySQL server and can perform SQL queries:

        Show databases;

- **Output**

![output](./Image/output%20of%20client%20database.png)
