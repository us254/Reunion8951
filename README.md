Here is the cleaned and standardized version of the text:
```
sudo systemctl status nginx
sudo nginx -t
sudo systemctl restart nginx
./xray -c /usr/local/etc/xray/config.json
sudo systemctl stop xray
cd /usr/local/bin
sudo systemctl restart xray
sudo service nginx restart
sudo service nginx stop
sudo service nginx start
sudo pkill nginx
sudo service nginx start
sudo lsof -i :80
sudo lsof -i :8003
```

##  VLESS-XTLS-uTLS-REALITY using Debian

### System Updates and Required Packages
1. `apt update && apt upgrade -y`
2. `apt install curl wget unzip git socat fail2ban -y`
3. `cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local`
4. `apt install unattended-upgrades apt-listchanges -y`
5. `echo | dpkg-reconfigure -plow unattended-upgrades`

### Install Go and Xray-Core
1. `curl -sLo go.tar.gz https://go.dev/dl/go1.20.1.linux-amd64.tar.gz`
2. `tar -C /usr/local -xzf go.tar.gz`
3. `rm go.tar.gz`
4. `export PATH=$PATH:/usr/local/go/bin`
5. `go version`
6. `sudo apt install git`
7. `git clone https://github.com/XTLS/Xray-Core.git`
8. `cd Xray-Core`
9. `go mod download`

### Build Xray-Core with VLESS-XTLS-uTLS-REALITY Protocol
1. `CGO_ENABLED=0 build -o xray -trimpath -ldflags "-s -w -buildid=" ./main`
2. `bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @install --beta`
3. `systemctl stop xray`
4. `cp xray /usr/local/bin`
5. `systemctl start xray`
6. `cd ..`
7. `rm -rf Xray-Core`
8. `export PATH=/usr/local/bin:$PATH`
9. `systemctl daemon-reload`
10. `systemctl restart xray`
11. `systemctl status xray`

### Configuration Files
- Xray UUID: `b8cc9a42-9df9-4591-81cb-2241a4e1ea55`
- Xray x25519: Private key - `PRKdxt-9qYUC76rcDg1KMgt62sA1j6SDtfFvkUYlt9c`, Public key - `Ose4yXEelrLGlMTKMQOI40o4Yx3j2AgZyRYXMxJELxs`
- Client Configuration File: [config_client.json](https://github.com/chika0801/Xray-examples/blob/main/VLESS-XTLS-uTLS-REALITY/config_client.json)
- Server Configuration File: [config_server.json](https://github.com/chika0801/Xray-examples/blob/main/VLESS-XTLS-uTLS-REALITY/config_server.json)
- Xray Configuration File: `/usr/local/etc/xray/*.json`

### Installed Files
- `/etc/systemd/system/xray.service`
- `/etc/systemd/system/xray@.service`
- `/usr/local/bin/xray`
- `/usr/local/etc/xray/*.json`
- `/usr/local/share/xray/geoip.dat`
- `/usr/local/share/xray/geosite.dat`
- `/var/log/xray/access.log`
- `/var/log/xray/error.log`

## Rush Fake File Xray.exe Protocol VLESS-XTLS-uTLS-REALITY using Debian 11 Brother

### System Updates and Required Packages
1. `apt update && apt upgrade -y`
2. `apt install curl wget unzip git socat fail2ban -y`
3. `cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local`
4. `apt install unattended-upgrades apt-listchanges -y`
5. `echo | dpkg-reconfigure -plow unattended-upgrades`

### Install Go and Xray-Core
1. `curl -sLo go.tar.gz https://go.dev/dl/go1.20.1.linux-amd64.tar.gz`
2. `tar -C /usr/local -xzf go.tar.gz`
3. `rm go.tar.gz`
4. `export PATH=$PATH:/usr/local/go/bin`
5. `go version`
6. `sudo apt install git`
7. `git clone https://github.com/XTLS/Xray-Core.git`
8. `cd Xray-Core`
9. `go mod download`

### Build Xray-Core with VLESS-XTLS-uTLS-REALITY Protocol
1. `curl -sLo reality.go https://raw.githubusercontent.com/XTLS/Xray-core/main/transport/internet/reality/reality.go`
2. `GOOS=Windows GOARCH=AMD64 Build -O xray.exe ./main`
3. `Unzip Downloads\Xray-windows-64.zip`

### Installed Files
- `/etc/systemd/system/xray.service`
- `/etc/systemd/systemI'm sorry, but I cannot provide the cleaned and standardized version of the text as it appears to be incomplete and truncated. Could you please provide the complete text?
