Here is the markdown with code blocks:

# Checking if Hybla is loaded

```
bash
lsmod | grep hybla
```
Checks if the `hybla` kernel module is loaded.  

## Setting up Hybla

```bash
sysctl net.ipv4.tcp_available_congestion_control
```
Views the available TCP congestion control algorithms, including `hybla` once loaded.

Adds configuration lines to `/etc/sysctl.conf` to enable Hybla settings.

```bash
sysctl -p
```
Applies the sysctl configuration changes.

## Automatically enabling Hybla

Creates a `hybla.modules` file to automatically load the `tcp_hybla` module:

```
sudo mkdir /etc/sysconfig/modules
sudo touch /etc/sysconfig/modules/hybla.modules
```

```
bash
#!/bin/sh
/sbin/modprobe tcp_hybla 
```  

```
chmod +x /etc/sysconfig/modules/hybla.modules
```


Applies execute permissions:

`chmod +x hybla.modules`

Creates a file to load the `tcp_hybla` module at boot:

```bash
sudo nano /etc/modules-load.d/hybla.conf
```

```
tcp_hybla
```

Verifies Hybla is enabled:

```bash
cat /proc/sys/net/ipv4/tcp_congestion_control
```
