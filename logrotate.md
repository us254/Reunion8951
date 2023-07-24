Here are the steps with code blocks to configure log rotation and compression for Xray logs on Debian:

# Create logrotate config

1. Create `/etc/logrotate.d/xray`

2. Add config:

    ```
    /var/log/xray/access.log {
        daily
        missingok
        rotate 30
        compress
        delaycompress
        notifempty
        create 0600 nobody nogroup
    }

    /var/log/xray/error.log {
        daily
        missingok
        rotate 30
        compress
        delaycompress 
        notifempty
        create 0600 nobody nogroup
    }
    ```

3. Test config:

    ```bash
    logrotate -d /etc/logrotate.d/xray
    ```

# Setup systemd service and timer

4. Create systemd service `/etc/systemd/system/logrotate@xray.service`:

    ```
    [Unit]
    Description=Rotate Xray logs

    [Service]
    Type=oneshot
    ExecStart=/usr/sbin/logrotate /etc/logrotate.d/xray
    ```

5. Create systemd timer `/etc/systemd/system/logrotate@xray.timer`:

    ```
    [Unit]
    Description=Run logrotate daily for Xray logs

    [Timer] 
    OnCalendar=*-*-* 06:10:00
    Persistent=true
   
    [Install]
    WantedBy=timers.target
    ```

6. Enable timer:

    ```bash
    systemctl enable --now logrotate@xray.timer
    ```

This will run the logrotate service daily at 6:10 AM.

Let me know if you need any clarification or have additional questions!
