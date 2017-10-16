# 1. Swappiness

## Set swappiness on all nodes
```
echo 'vm.swappiness = 1' >> /etc/sysctl.conf
sysctl vm.swappiness=1
```

## Get the swappiness values
```
COMMAND="cat /etc/sysctl.conf | grep vm.swappiness"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done

vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
```

# 2. Mounted volumes
## Note for 2. and 3. exercises:
When I created the EC2 instances I reserved 50 GB gp2 volumes. This is the reason I didn't attach more disks to the nodes. Instead of I expanded the root partitions from the deafult 8 GB size to 50 GB. I used the 'fdisk /dev/xvda' command.
If I would made a production cluster, I would attach more disks for the hosts (I would change fstab config file for it).

```
COMMAND="lsblk"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
NAME    MAJ:MIN RM SIZE RO TYPE MOUNTPOINT
xvda    202:0    0  50G  0 disk
└─xvda1 202:1    0  50G  0 part /
```

# 3. Free spaces

```
COMMAND="df -h"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done

Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  789M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  789M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  789M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  789M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  789M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```