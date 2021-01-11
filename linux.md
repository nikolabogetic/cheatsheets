# Linux

List services

```
systemctl list-unit-files --state=enabled
```

https://github.com/oguzhaninan/Stacer


Firewalld

```
firewall-cmd --state
firewall-cmd --list-all
firewall-cmd --get-default-zone
firewall-cmd --zone=public --permanent --add-service=https
firewall-cmd --zone=public --permanent --add-port=5000/tcp
firewall-cmd --zone=public --permanent --remove-port=5000/tcp
firewall-cmd --list-services
firewall-cmd --list-ports
firewall-cmd --reload
```

For nginx proxy pass
```
setsebool httpd_can_network_connect 1 -P
```

LVM

```

lsblk

pvscan

pvs
vgs
lvs

vgdisplay -v
lvdisplay

lvextend -L +10G /dev/centos/root
lvextend -l +100%FREE /dev/centos/root

# xfs
xfs_growfs /dev/centos/root

# ext4
resize2fs /dev/centos/root


```








```
hostnamectl set-hostname <new hostname>
```


Centos

Edit active repos
```
cd /etc/yum.repos.d
# vim repo -> change enabled to 0
yum repolist
```

YUM
```
yum list available
yum list installed
yum list all
yum list kernel
yum repolist
yum autoremove <package>
yum install <package> --enablerepo=<repo>
```


Users
```
# High level command with home folder creation
adduser <username>

# Delete user and home folder
userdel -r <username>
```

Chkconfig
```
chkconfig --list
chkconfig --del <service>
```

```
systemctl daemon-reload
```


Search root partition only
```
find / -xdev -name <file>
```

