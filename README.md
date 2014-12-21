sqlite2mysql
============

Script to convert from sqlite3 to mysql

This script is based on the scripts found in this webpage:
http://www.redmine.org/boards/2/topics/12793?r=24999

To use it, just dump the sqlite database with the following command:
sqlite3 bbdd.sqlite .dump > bbdd.sql

Execute the script to convert the bbdd.sql file to a MySQL compatible file:
./sqlite2mysql.py bbdd.sql > bbdd.mysql

The script doesn't adapt the sqlite3 field types to MySQL, so you should check wether all the CREATE TABLE statements have a data type that makes sense in MySQL. You should change to VARCHAR(XX) and to DECIMAL(x,Y) the undefined and REAL sqlite types.

Then you need to import the file into de MySQL database:
mysql -u user -p database < bbdd.mysql
