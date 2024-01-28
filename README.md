# MySQL Coffee Database Project

This repository hosts a MySQL project that includes a database related to coffee. Designed to demonstrate basic MySQL operations and database management, this project is particularly suited for those interested in learning MySQL within a Linux environment. It was created in a Linux Ubuntu environment hosted on a Linode VM, using command-line tools.

## Project Overview

The project revolves around a MySQL database named `nc_coffee`, which contains 3 tables: `coffee_table`, `avengers`, and `orders`.

- **coffee_table**: This table is structured to hold data about different types of coffee, characterized by attributes like region and roast. It's designed to provide a simple demonstration of data storage and retrieval in a relational database.

- **avengers**: This table contains a list of characters, presumably from the popular Avengers series. It includes details such as their first and last names, origin, age, alias, and an attribute indicating whether they have a beard. This table serves as a fun and engaging way to demonstrate data manipulation and querying in MySQL.

- **orders**: This table is used to link the `avengers` and `coffee_table` tables together. It includes an `order_id` as the primary key and foreign keys `avengers_id` and `coffee_id` to establish relationships between orders, avengers, and coffee types. This table demonstrates the concept of relational databases.

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

| Tables_in_nc_coffee |
|---------------------|
| avengers            |
| coffee_table        |


6. **View Contents of `coffee_table`**:
SELECT * FROM coffee_table;

| id | name          | region   | roast   |
|----|---------------|----------|---------|
| 1  | default route | ethopia  | light   |
| 2  | docker run    | mexico   | medium  |
| 3  | helpdesk      | honduras | medium  |
| 4  | on-call       | peru     | dark    |
| 5  | ifconfig      | tanzania | blonde  |
| 6  | traceroute    | bali     | med-dark|


or

SELECT * FROM avengers;

| id | first_name | last_name | origin   | age  | alias             | beard |
|----|------------|-----------|----------|------|-------------------|-------|
| 1  | thor       | odinson   | asgard   | 1500 | strongest avenger | 1     |
| 2  | clint      | barton    | earth    | 35   | hawkeye           | NULL  |
| 3  | tony       | stark     | earth    | 52   | iron man          | NULL  |
| 4  | peter      | parker    | earth    | 17   | spiderman         | NULL  |
| 5  | groot      | NULL      | planet x | 18   | tree              | 0     |

or 

SELECT * FROM orders;

| order_id | avengers_id | coffee_id | quantity |
|----------|-------------|-----------|----------|
|    1     |     3       |     1     |    1     |
|    2     |     1       |     5     |    1     |
|    3     |     2       |     2     |    1     |
|    4     |     4       |     4     |    1     |

7. **Describe Table Structure**:
DESCRIBE coffee_table;

| Field  | Type         | Null | Key | Default | Extra |
|--------|--------------|------|-----|---------|-------|
| id     | int          | YES  |     | NULL    |       |
| name   | varchar(255) | YES  |     | NULL    |       |
| region | varchar(255) | YES  |     | NULL    |       |
| roast  | varchar(255) | YES  |     | NULL    |       |


## Exiting MySQL

To exit the MySQL interface, simply type `exit` or `\q`.
