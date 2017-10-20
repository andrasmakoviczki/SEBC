# Clouder Provider
AWS

# Linux release

CentOS 6 (x86_64) - with Updates HVM
(AMI: CentOS Linux 6 x86_64 HVM EBS 1704_01-74e73035-3435-48d6-88e0-89cc02ad83ee-ami-23285c35.4 (ami-322af45d))

```
[root@ip-172-32-6-77 ~]# lsb_release -a
```

```
LSB Version:    :base-4.0-amd64:base-4.0-noarch:core-4.0-amd64:core-4.0-noarch
Distributor ID: CentOS
Description:    CentOS release 6.9 (Final)
Release:        6.9
Codename:       Final
```

# Disk space

```
COMMAND="df -h"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  898M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  897M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  898M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  898M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1       50G  897M   46G   2% /
tmpfs           7.3G     0  7.3G   0% /dev/shm
```

# Yum list

```
yum repolist enabled
```

```
Loaded plugins: fastestmirror, presto
Loading mirror speeds from cached hostfile
 * base: mirror.fra10.de.leaseweb.net
 * extras: mirror.imt-systems.com
 * updates: mirror.imt-systems.com
repo id                                                     repo name                                                              status
base                                                        CentOS-6 - Base                                                        6,706
extras                                                      CentOS-6 - Extras                                                         46
updates                                                     CentOS-6 - Updates                                                       723
repolist: 7,475
```

# Users and groups

```
[root@ip-172-32-9-75 ~]# cat /etc/passwd | grep "ernest\|siwicki"
```

```
ernest:x:2000:3001::/home/ernest:/bin/bash
siwicki:x:3000:3002::/home/siwicki:/bin/bash
```

```
[root@ip-172-32-9-75 ~]# cat /etc/group | grep "usa\|emea"
```

```
usa:x:3001:ernest
emea:x:3002:siwicki
```