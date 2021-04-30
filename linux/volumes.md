LVM
```
lsblk
pvscan

pvs
vgs
lvs

vgdisplay -v
lvdisplay

lvm pvcreate /dev/sdb1
lvm vgcreate vg_docker /dev/sdb1
lvm lvcreate -n <myvolume> -L 8G <myvolumegroup>

lvextend -L +10G /dev/centos/root
lvextend -l +100%FREE /dev/centos/root

# xfs
xfs_growfs /dev/centos/root

# ext4
resize2fs /dev/centos/root

# Deleting
lvremove /dev/centos/root
vgremove /dev/<myvolumegroup>
pvremove /dev/sdb1
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


```

Fdisk
```
# Create partition
fdisk /dev/sdb
n
p
t
8e
w
partprobe
lsblk
```

```
# Delete partition
fdisk /dev/sdb1
d
w
partprobe
lsblk
```

Create file system
```
mkfs.ext4 /dev/<myvolumegroup>/<myvolume>
# could also use xfs
```

Fstab
```
blkid
# copy uuid
# create mount dir at /mnt/local-storage/<storage-class-name>/<volume>
# add entry to fstab (uuid or /dev/mapper/...)
mount -a
```




