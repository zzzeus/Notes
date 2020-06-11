# Commands of Linux

This is a note about Commands used in Linux
1. [Quick look](#Quick_look)
2. [Package Management](Package_Management)

## Quick look
```bash
###### copy and move   ############

# copy directory and all its files
cp -avr [source] [destination]

# cp the files and subdirectory 
cp -v [source]/* [destination]

# move 
mv [source] [destination]

# remove file and directory
rm -r [folder]
rm *.txt

####### unzip and zip   ##########

unzip filename.zip -d /path/to/directory

# no print 
unzip -q filename.zip

# with a password
unzip -P PasswOrd filename.zip

# get information
unzip -l filename.zip

# unzip a.zip001,a.zip002...
cat file.zip* > file.zip
unzip file.zip

tar –xvf file.tar 

tar –xzf file.tar.gz

####### path     ##############

# return home path
cd ~

# show current path
pwd

# read txt
head [path]

```

## Package Management
```bash
# Package 
rpm -qa # look at all package installed
rpm -qa |grep mysql # search mysql package

rpm -ivh your-package # install package directly
rpm -e your-package          # uninstall
rpm -e --nodeps your-package # uninstall 
```

## Sql
### basic information of mysql
```sql
# check sql status
systemctl status mysqld
ps -ef | grep mysqld

# check version
mysqladmin --version

# open mysql
mysql -u root -pPASSWORD

# shut down mysql
mysqladmin -u root -p shutdown

# set password
mysqladmin -u root password "new_password";

```

* Basic operation
```sql
# show all databases
SHOW DATABASES;

# change to the database
USE MY_DATABASE;

# show all tables
SHOW TABLES;

SHOW COLUMNS FROM user;


``` 
* operation on one table
```sql
# create a database
CREATE DATABASE name;


 create table if not exists 'websites'(
 'id' INT UNSIGNED AUTO_INCREMENT,
 'title' VARCHAR(100) NOT NULL,
 'author' VARCHAR(40) NOT NULL,
 'submission_date' DATE,
 PRIMARY KEY ('id')
 )ENGINE=InnoDB DEFAULT CHARSET=utf8;

 CREATE TABLE IF NOT EXISTS `runoob_tbl`(
    `runoob_id` INT UNSIGNED AUTO_INCREMENT,
    `runoob_title` VARCHAR(100) NOT NULL,
    `runoob_author` VARCHAR(40) NOT NULL,
    `submission_date` DATE,
    PRIMARY KEY ( `runoob_id` )
 )ENGINE=InnoDB DEFAULT CHARSET=utf8;
```