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
```

```
vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
vm.swappiness = 1
```

# 2. Mounted volumes
## Note for 2. and 3. exercises
When I created the EC2 instances I reserved 50 GB gp2 volumes. This is the reason I didn't attach more disks to the nodes. Instead of I expanded the root partitions from the default 8 GB size to 50 GB. I used the 'fdisk /dev/xvda' command.
If I would made a production cluster, I would attach more disks for the hosts (I would change fstab config file for it).

```
COMMAND="lsblk"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
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
```

```
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

# 4. Transparent hugepage
## Disable the hugepage

```
echo never > /sys/kernel/mm/transparent_hugepage/defrag;
echo never > /sys/kernel/mm/transparent_hugepage/enabled;
```

## Get the hugepage files content

```
COMMAND="echo -e \"$(cat /sys/kernel/mm/transparent_hugepage/defrag)\t$(cat /sys/kernel/mm/transparent_hugepage/enabled)\""; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
always madvise [never]  always madvise [never]
always madvise [never]  always madvise [never]
always madvise [never]  always madvise [never]
always madvise [never]  always madvise [never]
always madvise [never]  always madvise [never]
```

# Network interfaces

```
COMMAND="/sbin/ip addr"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:f8:e9:d8:e9:14 brd ff:ff:ff:ff:ff:ff
    inet 172.32.9.69/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::f8:e9ff:fed8:e914/64 scope link
       valid_lft forever preferred_lft forever
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:94:ae:b5:88:52 brd ff:ff:ff:ff:ff:ff
    inet 172.32.4.188/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::94:aeff:feb5:8852/64 scope link
       valid_lft forever preferred_lft forever
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:dd:12:02:0c:5c brd ff:ff:ff:ff:ff:ff
    inet 172.32.1.46/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::dd:12ff:fe02:c5c/64 scope link
       valid_lft forever preferred_lft forever
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:46:9e:d7:f5:ce brd ff:ff:ff:ff:ff:ff
    inet 172.32.7.140/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::46:9eff:fed7:f5ce/64 scope link
       valid_lft forever preferred_lft forever
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 02:1d:6d:f4:2f:7c brd ff:ff:ff:ff:ff:ff
    inet 172.32.0.33/20 brd 172.32.15.255 scope global eth0
    inet6 fe80::1d:6dff:fef4:2f7c/64 scope link
       valid_lft forever preferred_lft forever
```

# Hosts lookup

## getent forward lookup

```
COMMAND="getent hosts $HOSTS"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
```

## gentent reverse lookup

```
COMMAND="getent hosts $HOSTS"; \
IPS="172.32.9.69 172.32.4.188 172.32.1.46 172.32.7.140 172.32.0.33"; \
for i in $IPS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
172.32.9.69     ip-172-32-9-69.eu-central-1.compute.internal node0
172.32.4.188    ip-172-32-4-188.eu-central-1.compute.internal node1
172.32.1.46     ip-172-32-1-46.eu-central-1.compute.internal node2
172.32.7.140    ip-172-32-7-140.eu-central-1.compute.internal node3
172.32.0.33     ip-172-32-0-33.eu-central-1.compute.internal node4
```
