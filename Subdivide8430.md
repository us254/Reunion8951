# Setting up Hybla

```markdown
**lsmod | grep hybla**

Step 2: Setting up Hybla  

View the available congestion algorithms using the command below. Once Hybla has been loaded, it will appear.  

**sysctl net.ipv4.tcp_available_congestion_control**

Add the following lines to */etc/sysctl.conf*.
```

The config lines are omitted for brevity.

``` markdown
Use the command to enable the change.

**sysctl -p**  

Hybla is now enabled.

You can also use the following steps to automatically enable this algorithm.   

Add a hybla.modules file to the */etc/sysconfig/modules* directory and enter the content below:

```bash
#!/bin/sh  
/sbin/modprobe tcp_hybla
```

```markdown  
Then grant the file execution privileges:

**chmod +x hybla.modules**  

**sudo nano /etc/modules-load.d/hybla.conf**

This will open a text editor (nano) and create a new file named `hybla.conf` in the `/etc/modules-load.d/` directory.

```bash
tcp_hybla
```

```markdown
This will tell the system to load the `tcp_hybla` module at boot time.

**cat /proc/sys/net/ipv4/tcp_congestion_control** 
```
