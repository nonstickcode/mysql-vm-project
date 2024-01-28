# MySQL Coffee Database Project

This repository hosts a MySQL project that includes a database related to coffee. It's designed to demonstrate basic MySQL operations and database management within a Linux environment, specifically tailored for those interested in learning MySQL.  This project was created in a Linode VM Linux Ubuntu environment using command line.

## Project Overview

The project revolves around a MySQL database named `nc_coffee`, which contains 2 tables including `coffee_table` and 'avengers'. The 'coffee_table' table is structured to hold data about different types of coffee, characterized by attributes like region and roast.

## Getting Started

To try out this project, you'll need to have MySQL installed on your system. You can clone this repository and import the provided SQL files into your MySQL environment.

### Prerequisites

- MySQL installed on your system.
- Git for cloning the repository.

### Clone the Repository

git clone https://github.com/nonstickcode/mysql-vm-project.git
cd mysql-vm-project

### Importing the Database

After cloning the repository, you can import the database into MySQL using the `root` user. If you have set up another user with the necessary privileges, you can use that user instead.

Run the following command in the terminal: mysql -u root -p < path/to/sql_file.sql

- Replace `root` with your MySQL username if you are not using the `root` user.
- Replace `path/to/sql_file.sql` with the actual path to the SQL file in the cloned repository.
- After executing the command, you will be prompted to enter the password for the MySQL user.

**Note**: Using the `root` user for MySQL operations is not recommended for production environments due to security risks. It's better to create a specific MySQL user with limited permissions for routine tasks.

## Exploring the Database

Once imported, you can explore the database using MySQL commands. See the development section below in this file for detailed instructions on interacting with the database.

## License

This project is licensed under the [MIT License](LICENSE).



***



# Developer Guide for MySQL Coffee Database Project

This guide is intended for developers or users who wish to interact directly with the MySQL database included in this project.

## Accessing and Using the MySQL Database

Follow these steps to access and use the `nc_coffee` database:

### Connecting to MySQL

1. **SSH into the VM**:
   - Use the SSH command provided in your Linode server information to connect to your VM.

2. **Check MySQL Server Status**:
   - Run `sudo systemctl status mysql` to check the MySQL server status.
   - Press `Q` to exit the status screen.

3. **Access MySQL**:
   - Use `sudo mysql` to enter the MySQL command line.

### Basic MySQL Operations

Once inside MySQL, perform the following operations:

1. **Show All Databases**:
SHOW DATABASES;

2. **Select the `nc_coffee` Database**:
USE nc_coffee;

4. **Display Tables in the Database**:
SHOW TABLES;

mysql> show tables;

| Tables_in_nc_coffee |
|---------------------|
| avengers            |
| coffee_table        |


6. **View Contents of `coffee_table`**:
SELECT * FROM coffee_table;

or

SELECT * FROM avengers;

mysql> SELECT * FROM avengers;

| id | first_name | last_name | origin   | age  | alias             | beard |
|----|------------|-----------|----------|------|-------------------|-------|
| 1  | thor       | odinson   | asgard   | 1500 | strongest avenger | 1     |
| 2  | clint      | barton    | earth    | 35   | hawkeye           | NULL  |
| 3  | tony       | stark     | earth    | 52   | iron man          | NULL  |
| 4  | peter      | parker    | earth    | 17   | spiderman         | NULL  |
| 5  | groot      | NULL      | planet x | 18   | tree              | 0     |


7. **Describe Table Structure**:
DESCRIBE coffee_table;

mysql> describe coffee_table;

| Field  | Type         | Null | Key | Default | Extra |
|--------|--------------|------|-----|---------|-------|
| id     | int          | YES  |     | NULL    |       |
| name   | varchar(255) | YES  |     | NULL    |       |
| region | varchar(255) | YES  |     | NULL    |       |
| roast  | varchar(255) | YES  |     | NULL    |       |


## Exiting MySQL

To exit the MySQL interface, simply type `exit` or `\q`.
