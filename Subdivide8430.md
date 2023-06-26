Here is the markdown text:

```
lsmod | grep hybla

Step 2: Setting up Hybla

sysctl net.ipv4.tcp_available_congestion_control  

net.ipv4.tcp_syncookies = 1  
net.ipv4.tcp_tw_reuse = 1 
net.ipv4.tcp_tw_recycle = 1
net.ipv4.tcp_fin_timeout = 30
net.ipv4.tcp_keepalive_time = 1200
net.ipv4.ip_local_port_range = 10000 65000  
net.ipv4.tcp_max_syn_backlog = 8192   
net.ipv4.tcp_max_tw_buckets = 5000
net.core.rmem_max = 67108864    
net.core.wmem_max = 67108864
net.ipv4.tcp_rmem = 4096 87380 67108864
net.ipv4.tcp_wmem = 4096 65536 67108864
net.core.netdev_max_backlog = 250000  
net.ipv4.tcp_mtu_probing=1
net.ipv4.tcp_congestion_control=hybla

sysctl -p
```

Hope this helps! Let me know if you have any other questions.
