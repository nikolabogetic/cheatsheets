Create a read only user

```
GRANT SELECT ON database.* TO 'username'@'host' IDENTIFIED BY 'password';

```

Create new db and user
```
CREATE DATABASE 'yourDB';
CREATE USER 'user1'@localhost IDENTIFIED BY 'password1';
GRANT ALL PRIVILEGES ON 'yourDB'.* TO 'user1'@localhost;
FLUSH PRIVILEGES;
```
