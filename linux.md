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
firewall-cmd --list-services
firewall-cmd --list-ports
firewall-cmd --reload
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

xfs_growfs /dev/centos/root


```












