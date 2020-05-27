# Postgres

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
