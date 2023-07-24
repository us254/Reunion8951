Here are the steps with code blocks to install xanmod-rt-x64v4 kernel and enable BBR2 + FQ-PIE on Ubuntu 22.04:

# Import XanMod Archive Key

1. Copy key to `/root/archive.key`

    ```bash
    curl -o /root/archive.key https://dl.xanmod.org/archive.key
    ```

2. Install gnupg

    ```bash
    sudo apt-get install gnupg
    ```

3. Import key

    ```bash    
    sudo gpg --dearmor -o /usr/share/keyrings/xanmod-archive-keyring.gpg /root/archive.key
    ```

# Add XanMod Repo

4. Add repo

    ```bash
    echo 'deb [signed-by=/usr/share/keyrings/xanmod-archive-keyring.gpg] http://deb.xanmod.org releases main' | sudo tee /etc/apt/sources.list.d/xanmod-release.list
    ```

5. Update and install kernel

    ```bash
    sudo apt update && sudo apt install linux-xanmod-rt-x64v4
    ``` 

6. Reboot

    ```bash
    sudo reboot
    ```

7. Check version

    ```bash
    uname -a
    ```

# Enable BBR2 + FQ-PIE

8. Enable BBR2

    ```bash
    sysctl -w net.core.default_qdisc=fq_pie
    echo "net.core.default_qdisc=fq_pie" >> /etc/sysctl.conf
    
    sysctl -w net.ipv4.tcp_congestion_control=bbr2
    echo "net.ipv4.tcp_congestion_control=bbr2" >> /etc/sysctl.conf
    ```

9. Load FQ-PIE

    ```bash
    tc qdisc add dev eth0 root fq_pie
    ```

10. Check status

    ```bash
    sysctl net.core.default_qdisc
    tc qdisc show dev eth0
    
    sysctl net.ipv4.tcp_congestion_control
    ```

Let me know if you need any clarification or have additional questions!
