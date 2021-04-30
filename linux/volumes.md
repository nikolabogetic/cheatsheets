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

# Deleting
lvremove /dev/centos/root
```

Partitioning
```
# Scan vm drives
ls /sys/class/scsi_host/ | while read host ; do echo "- - -" > /sys/class/scsi_host/$host/scan ; done

parted /dev/sdb
(parted) mklabel gpt
(parted) mkpart
Partition name?  []? dockerpart
File system type?  [ext2]? ext4
Start? 1
End? -1
(parted) quit

# lvm pvcreate /dev/sdb1
# lvm vgcreate vg_docker /dev/sdb1
```
