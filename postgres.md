# Postgres

Installation:
```
yum install https://download.postgresql.org/pub/repos/yum/reporpms/EL-7-x86_64/pgdg-redhat-repo-latest.noarch.rpm --nogpgcheck
yum install postgresql12-server
/usr/pgsql-12/bin/postgresql-12-setup initdb
systemctl enable postgresql-12
systemctl start postgresql-12
firewall-cmd --add-service=postgresql --permanent

vim /var/lib/pgsql/12/data/postgresql.conf
systemctl restart postgresql-12
```



Create user and db via PSQL:

```
CREATE DATABASE <dbname>;
CREATE USER <username> WITH ENCRYPTED PASSWORD '<password>';
GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <username>;
```

Create user and db in terminal:

```
createuser <username>
createdb <dbname>
```

Then in PSQL:

```
ALTER USER <username> WITH ENCRYPTED PASSWORD '<password>';
GRANT ALL PRIVILEGES ON DATABASE <dbname> TO <username>;
```



Commands

```
\list
\connect <dbname>
```


```
systemctl restart postgresql-11
```

Alter default privileges

```
ALTER DEFAULT PRIVILEGES IN SCHEMA myschema GRANT SELECT ON TABLES TO myuser;
```
