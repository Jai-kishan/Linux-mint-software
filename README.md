# Linux-software
how to install Linux mint basic software using termianl

# sublime
* Open a terminal and use the command below to install the GPG key.
```
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - 
```

* After that, create add the repository in your sources.list.
```
echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list
```

* Now refresh the package list and install Sublime Text.
```
sudo apt update && sudo apt install sublime-text
```

# Ipython
```
sudo apt install ipython
```

# Ipython3
```
sudo apt install ipython3
```

# Virtual Enviourment Install
```
sudo apt install virtualenv
```

# Virtual Enviourment Create
* python-2
```
virtualenv enviourment_name -p python
```

* python-3
```
virtualenv enviourment_name -p python3
```
# FileZilla
```
https://www.computernetworkingnotes.com/linux-tutorials/how-to-install-filezilla-ftp-client-in-ubuntu.html
```

# Termius
```
https://termius.com/linux
```

# GIT
```
sudo apt install git
```
# MongoDB compass
follow this ling :- 
```
https://www.mongodb.com/try/download/compass
````

# Robo 3t download and setup
```
https://stackoverflow.com/questions/35547860/how-to-install-robomongo-from-tar-gz-file-as-a-program-in-ubuntu-15-10
```
Robomongo is now Robo 3T. Following are the updated steps:

Download the tar file from robomongo site. The current file is robo3t-1.1.1-linux-x86_64-c93c6b0.tar.gz, but yours could be different.

Open up the terminal, switch to download directory and run the following commands:
```
$ tar -xvzf robo3t-1.1.1-linux-x86_64-c93c6b0.tar.gz
$ sudo mkdir /usr/local/bin/robomongo
$ sudo mv  robo3t-1.1.1-linux-x86_64-c93c6b0/* /usr/local/bin/robomongo
$ cd /usr/local/bin/robomongo/bin
$ sudo chmod +x robo3t 
$ sudo gedit ~/.bashrc
```
Add the following line to the end of .bashrc file:
```
alias robomongo='/usr/local/bin/robomongo/bin/robo3t'
```
Save and close the file. Now reload it using the following command:
```
$ source ~/.bashrc
```
Then you can run robomongo from your terminal and it will work:
```
$ robomongo
```

# How To Install MySQL on Ubuntu 18.04

* Step 1 — Installing MySQL
```
sudo apt update
sudo apt install mysql-server
```

* Step 2 — Configuring MySQL
```
sudo mysql_secure_installation
```

* Step 3 — (Optional) Adjusting User Authentication and Privileges
```
$ sudo mysql
mysql>SELECT user,authentication_string,plugin,host FROM mysql.user;

Output
+------------------+-------------------------------------------+-----------------------+-----------+
| user             | authentication_string                     | plugin                | host      |
+------------------+-------------------------------------------+-----------------------+-----------+
| root             |                                           | auth_socket           | localhost |
| mysql.session    | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| mysql.sys        | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| debian-sys-maint | *CC744277A401A7D25BE1CA89AFF17BF607F876FF | mysql_native_password | localhost |
+------------------+-------------------------------------------+-----------------------+-----------+
4 rows in set (0.00 sec)
```

* This command will change the root password
```
mysql>ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

* Then, run FLUSH PRIVILEGES which tells the server to reload the grant tables and put your new changes into effect:
```
mysql> FLUSH PRIVILEGES;
```
* Check the authentication methods employed by each of your users again to confirm that root no longer authenticates using the auth_socket plugin:
```
SELECT user,authentication_string,plugin,host FROM mysql.user;
```
* Output
```
+------------------+-------------------------------------------+-----------------------+-----------+
| user             | authentication_string                     | plugin                | host      |
+------------------+-------------------------------------------+-----------------------+-----------+
| root             | *3636DACC8616D997782ADD0839F92C1571D6D78F | mysql_native_password | localhost |
| mysql.session    | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| mysql.sys        | *THISISNOTAVALIDPASSWORDTHATCANBEUSEDHERE | mysql_native_password | localhost |
| debian-sys-maint | *CC744277A401A7D25BE1CA89AFF17BF607F876FF | mysql_native_password | localhost |
+------------------+-------------------------------------------+-----------------------+-----------+
4 rows in set (0.00 sec)
```

```
mysql> exit
```

* mysql -u root -p

```
From there, create a new user and give it a strong password:
CREATE USER 'sammy'@'localhost' IDENTIFIED BY 'password';
GRANT ALL PRIVILEGES ON *.* TO 'sammy'@'localhost' WITH GRANT OPTION;
```

```
mysql>exit
```


* Step 4 — Testing MySQL
* Regardless of how you installed it, MySQL should have started running automatically. To test this, check its status.
```
systemctl status mysql.service
```

* You’ll see output similar to the following:

* Output
```
● mysql.service - MySQL Community Server
   Loaded: loaded (/lib/systemd/system/mysql.service; enabled; vendor preset: en
   Active: active (running) since Wed 2018-04-23 21:21:25 UTC; 30min ago
 Main PID: 3754 (mysqld)
    Tasks: 28
   Memory: 142.3M
      CPU: 1.994s
   CGroup: /system.slice/mysql.service
           └─3754 /usr/sbin/mysqld
If MySQL isn’t running, you can start it with sudo systemctl start mysql.
```


* sudo mysqladmin -p -u root version
* You should see output similar to this:

* Output
```
mysqladmin  Ver 8.42 Distrib 5.7.21, for Linux on x86_64
Copyright (c) 2000, 2018, Oracle and/or its affiliates. All rights reserved.

Oracle is a registered trademark of Oracle Corporation and/or its
affiliates. Other names may be trademarks of their respective
owners.

Server version      5.7.21-1ubuntu1
Protocol version    10
Connection      Localhost via UNIX socket
UNIX socket     /var/run/mysqld/mysqld.sock
Uptime:         30 min 54 sec

Threads: 1  Questions: 12  Slow queries: 0  Opens: 115  Flush tables: 1  Open tables: 34  Queries per second avg: 0.006
```
* This means MySQL is up and running.
