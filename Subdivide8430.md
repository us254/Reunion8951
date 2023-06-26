Here's the markdown version:

```
### Step 1: Check for Hybla

To check if Hybla has been loaded, use the following command:

```
lsmod | grep hybla
```

### Step 2: Setting up Hybla

View the available congestion algorithms using the command below. Once Hybla has been loaded, it will appear.

```
sysctl net.ipv4.tcp_available_congestion_control
```

Add the following lines to `/etc/sysctl.conf`.

```
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
```

Use the following command to enable the changes:

```
sysctl -p
```

Hybla is now enabled.

You can also use the following steps to automatically enable this algorithm.

Add a `hybla.modules` file to the `/etc/sysconfig/modules` directory and enter the content below:

```
#!/bin/sh
/sbin/modprobe tcp_hybla
```

Then grant the file execution privileges:

```
chmod +x hybla.modules
```

Use the following command to create a new file named `hybla.conf` in the `/etc/modules-load.d/` directory:

```
sudo nano /etc/modules-load.d/hybla.conf
```

Add the following line to the file:

```
tcp_hybla
```

This will tell the system to load the `tcp_hybla` module at boot time.

To check if Hybla is now the selected congestion control algorithm, use the following command:

```
cat /proc/sys/net/ipv4/tcp_congestion_control
```
