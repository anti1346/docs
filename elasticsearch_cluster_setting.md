### 
```
cat <<EOF >> /etc/hosts
### elasticsearch
192.168.56.71  node1
192.168.56.72  node2
192.168.56.73  node3
EOF
```

```
cat << EOF >> /etc/security/limits.conf

### elasticsearch
elasticsearch       hard    nofile   65535
elasticsearch       soft    nofile   65536
elasticsearch       hard    nproc    65536
elasticsearch       soft    nproc    65536
elasticsearch       hard    memlock  unlimited
elasticsearch       soft    memlock  unlimited
EOF
```

```
echo "vm.max_map_count = 262144" | sudo tee -a /etc/sysctl.conf
```
```
echo "vm.swappiness = 1" | sudo tee -a /etc/sysctl.conf
```
```
sudo sysctl -p
```

```
sudo swapoff -a
```
```
sudo sed -i '/swap/ s/^/#/' /etc/fstab
```


