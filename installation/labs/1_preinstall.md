#Swappiness

##Set swappiness on all nodes
```
echo 'vm.swappiness = 1' >> /etc/sysctl.conf
sysctl vm.swappiness=1
```

##Get the swappiness values
```
COMMAND="cat /etc/sysctl.conf | grep vm.swappiness"; \
HOSTS="node0 node1 node2 node3 node4"; \
for i in $HOSTS; do ssh -i BigDataSEBCkey.pem centos@$i $COMMAND; done
```


