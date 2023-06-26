
```
# Loading and Enabling Hybla Congestion Control Algorithm

To load and enable the Hybla congestion control algorithm on your system, follow these steps:

1. Check if the Hybla module is already loaded by running the command:

   ```
   lsmod | grep hybla
   ````

2. View the available congestion control algorithms on your system using the command:

   ```
   sysctl net.ipv4.tcp_available_congestion_control
   ````

   If Hybla is not listed, proceed with the following steps.

3. Add the following lines to `/etc/sysctl.conf`:

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
   net.ipv4.tcp_mtu_probing = 1
   net.ipv4.tcp_congestion_control = hybla
   ````

   These lines configure various TCP/IP parameters and set the congestion control algorithm to Hybla.

4. Apply the changes using the command:

   ```
   sysctl -p
   ````

5. Verify that Hybla is now enabled by running the command:

   ```
   cat /proc/sys/net/ipv4/tcp_congestion_control
   ````

   The output should be `hybla`.

6. (Optional) To automatically enable the Hybla algorithm at boot time, create a file named `hybla.conf` in the `/etc/modules-load.d/` directory and add the following line to the file:

   ```
   tcp_hybla
   ````

   Save the file and grant it execution privileges by running the command:

   ```
   chmod +x /etc/modules-load.d/hybla.conf
   ````

   This will load the `tcp_hybla` module at boot time.

That's it! Your system should now be using the Hybla congestion control algorithm.
```
