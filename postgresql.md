# How to Install PostgreSQL 9.6 on Ubuntu 18.04 LTS
**Step 1: Add PostgreSQL Apt Repository**

```
$ sudo sh -c 'echo "deb http://apt.postgresql.org/pub/repos/apt/ `lsb_release -cs`-pgdg main" >> /etc/apt/sources.list.d/pgdg.list'

$ wget -q https://www.postgresql.org/media/keys/ACCC4CF8.asc -O - | sudo apt-key add -
```

**Step 2: Install PostgreSQL**
```
$ sudo apt-get update
$ sudo apt-get upgrade
 
$ sudo apt-get install postgresql postgresql-contrib libpq-dev pgadmin3
```

**Step 3: Connecting to PostgreSQL**
* Ather the installation of PostgreSQL a user account called postgres created that is associated with the default Postgres role. In order log into to use Postgres account, we nee to give following command:

```
$ sudo su - postgres
$ psql
```

**To list the databases  type following command**
```
postgres-# \l
```

**The Command above will give you following output**

```
                                  List of databases
   Name    |  Owner   | Encoding |   Collate   |    Ctype    |   Access privileges   
-----------+----------+----------+-------------+-------------+-----------------------
 postgres  | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | 
 template0 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.UTF-8 | en_US.UTF-8 | =c/postgres          +
           |          |          |             |             | postgres=CTc/postgres
(3 rows)
```

**To list the user type following command**
```
postgres-# \du
```

**The Command above will give you following output**
```
                             List of roles
 Role name |                   Attributes                   | Member of 
-----------+------------------------------------------------+-----------
 postgres  | Superuser, Create role, Create DB, Replication | {}
```
 
**How to change PostgreSQL user password? type following command to change PostgreSQL:**
```
postgres=# ALTER USER postgres WITH PASSWORD 'test123';
ALTER ROLE
```

**To Create new user in PostgreSQL type following command:**
```
postgres=# CREATE USER user_1 WITH PASSWORD 'test123';
CREATE ROLE
```

**To upgrade a user to be a superuser in PostgreSQL type following command:**
```
postgres=# ALTER USER user_1 WITH SUPERUSER;
ALTER ROLE
```

**We can exit PostgreSQL prompt by typing following command:**
```
postgres-# \q
```

**To check login info use following command**
```
postgres-# \conninfo
```

**You can also follow this link**
[PostgreSQL](http://www.codebind.com/linux-tutorials/install-postgresql-9-6-ubuntu-18-04-lts-linux/)
