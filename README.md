# Reference
https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-22-04

# MySQL server setup
* Step 1: Installing MySQL
```
sudo apt update
sudo apt install mysql-server -y
sudo systemctl start mysql.service
```
* Step 2: Configuring MySQL
```
sudo mysql_secure_installation
```
* Step 3: Login to MySQL server
```
mysql -u root -p
```
* Step 4: create database with name csit and Create a dedicated MySQL user and granting privilges
```
CREATE DATABASE csit;
CREATE USER 'cloud'@'%' IDENTIFIED WITH mysql_native_password BY 'Cloud@123';
GRANT ALL ON *.* TO 'cloud'@'%';
FLUSH PRIVILEGES;
```
* Step 5: Create table and insert records
```
CREATE TABLE cloud_stones(
                stone_id VARCHAR(255) PRIMARY KEY,
                cloud_provider VARCHAR(25),
		cloud_account VARCHAR(25),
                region VARCHAR(50),
                stone_status VARCHAR(25)
                );
```
```
				
insert into cloud_stones(stone_id, cloud_provider, cloud_account, region, stone_status) values ('CSITAWS0001', 'AWS', '1234567891', 'us-east-1', 'provisioned');
```
