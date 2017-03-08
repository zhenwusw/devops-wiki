# PostgreSQL


* [PostgreSQL新手入门](http://www.ruanyifeng.com/blog/2013/12/getting_started_with_postgresql.html)

* [How to install Postgres in Ubuntu](https://www.digitalocean.com/community/tutorials/how-to-install-and-use-postgresql-on-ubuntu-14-04)


## How to create database quickly

```bash

$ sudo su postgres
$ createdb database-name
$ psql
$ postgres=# \l
$ postgres=# \c database-name
$ postgres=# ALTER DATABASE "database-name" OWNER TO user;
```
