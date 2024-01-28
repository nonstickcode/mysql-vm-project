# MySQL Coffee Database Project

This repository hosts a MySQL project that includes a database related to coffee. It's designed to demonstrate basic MySQL operations and database management within a Linux environment, specifically tailored for those interested in learning MySQL.

## Project Overview

The project revolves around a MySQL database named `nc_coffee`, which contains various tables including `coffee_table`. This table is structured to hold data about different types of coffee, characterized by attributes like region and roast.

## Getting Started

To try out this project, you'll need to have MySQL installed on your system. You can clone this repository and import the provided SQL files into your MySQL environment.

### Prerequisites

- MySQL installed on your system.
- Git for cloning the repository.

### Clone the Repository

git clone https://github.com/nonstickcode/mysql-vm-project.git
cd mysql-vm-project

### Importing the Database

After cloning the repository, you can import the database into MySQL:

mysql -u [username] -p < path/to/sql_file.sql

Replace `[username]` with your MySQL username and `path/to/sql_file.sql` with the path to the SQL file in the cloned repository.

## Exploring the Database

Once imported, you can explore the database using MySQL commands. See the `dev-readme.md` file in this repository for detailed instructions on interacting with the database.

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

go
Copy code

2. **Select the `nc_coffee` Database**:
USE nc_coffee;

markdown
Copy code

3. **Display Tables in the Database**:
SHOW TABLES;

go
Copy code

4. **View Contents of `coffee_table`**:
SELECT * FROM coffee_table;

markdown
Copy code

5. **Describe Table Structure**:
DESCRIBE coffee_table;

bash
Copy code

## Exiting MySQL

To exit the MySQL interface, simply type `exit` or `\q`.
