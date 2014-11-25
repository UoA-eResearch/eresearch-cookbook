---
layout: post
title:  “Connect to MySQL database”
date:   2014-11-25
categories: Recipe
---

### How to connect to MySQL database server from the command line
> *For a client program to be able to connect to the MySQL server, it must use the proper connection parameters, such as the name of the host where the server is running and the user name and password of your MySQL account. Each connection parameter has a default value, but you can override them as necessary using program options specified either on the command line or in an option file.

## Requirements
* MySQL server installed and running
* User must have access to the database (username and password required)

## Connect to the database server as below
* Open a terminal client
* Enter following command `mysql -h hostname -u myname -pmypass mydb`
  * hostname: the hostname or IP address of host where the server is running
  * myname: username to login to the database
  * mypass: password corresponding to the username. Make sure there is no space between ‘-p’ and the password following it
  * mydb: name of the database to connect

## Related info

For more details, check [MySQL server documentation] (http://dev.mysql.com/doc/refman/5.0/en/connecting.html).

@pguptanz
