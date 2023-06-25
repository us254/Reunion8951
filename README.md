```
# روش ساخت پروتکل VLESS-XTLS-uTLS-REALITY  با استفاده از Debian 11

1.  `apt update && apt upgrade -y`
2.  `apt install curl wget unzip git socat fail2ban -y`
3.  `cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local`
4.  `apt install unattended-upgrades apt-listchanges -y`
5.  `echo | dpkg-reconfigure -plow unattended-upgrades`

---

1.  `curl -sLo go.tar.gz https://go.dev/dl/go1.20.1.linux-amd64.tar.gz`
2.  `tar -C /usr/local -xzf go.tar.gz`
3.  `rm go.tar.gz`
4.  `export PATH=$PATH:/usr/local/go/bin`
5.  `go version`
6.  `sudo apt install -y git`
7.  `git clone https://github.com/XTLS/Xray-core.git`
8.  `cd Xray-core`
9.  `go mod download`

---

1.  `CGO_ENABLED=0 go build -o xray -trimpath -ldflags "-s -w -buildid=" ./main`
2.  `bash -c "$(curl -L https://github.com/XTLS/Xray-install/raw/main/install-release.sh)" @ install --beta`
3.  `systemctl stop xray`
4.  `cp xray /usr/local/bin`
5.  `systemctl start xray`
6.  `cd ..`
7.  `rm -rf go Xray-core`
8.  `export PATH=/usr/local/bin:$PATH`

---

1.  `systemctl daemon-reload`
2.  `systemctl restart xray`
3.  `systemctl status xray`

VLESS-XTLS-uTLS-REALITY
xray uuid
xray x25519  ———public_Key(client)/private_key(server)

config_client.json👇  
https://github.com/chika0801/Xray-examples/blob/main/VLESS-XTLS-uTLS-REALITY/config_client.json

config_server.json👇  
https://github.com/chika0801/Xray-examples/blob/main/VLESS-XTLS-uTLS-REALITY/config_server.json

/usr/local/etc/xray/*.json

---

# روش ساخت فایل xray.exe پروتکل VLESS-XTLS-uTLS-REALITY  با استفاده از Debian 11  برای
# استفاده در ویندوز سمت client

1.  `apt update && apt upgrade -y`
2.  `apt install curl wget unzip git socat fail2ban -y`
3.  `cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local`
4.  `apt install unattended-upgrades apt-listchanges -y`
5.  `echo | dpkg-reconfigure -plow unattended-upgrades`

---

1.  `curl -sLo go.tar.gz https://go.dev/dl/go1.20.1.linux-amd64.tar.gz`
2.  `tar -C /usr/local -xzf go.tar.gz`
3.  `rm go.tar.gz`
4.  `export PATH=$PATH:/usr/local/go/bin`
5.  `go version`
6.  `sudo apt install -y git`
7.  `git clone https://github.com/XTLS/Xray-core.git`
8.  `cd Xray-core`
9.  `go mod download`

---

1.  `curl -sLo reality.go https://raw.githubusercontent.com/XTLS/Xray-core/main/transport/internet/reality/reality.go`
2.  `GOOS=windows GOARCH=amd64 go build -o xray.exe ./main`
3.  `/root/Xray-core/`
4.  `geosite.dat`
5.  `geoip.dat`
6.  اجرای دستور زیر در powershell در ویندوز
    `./xray run -c config.json`

---

1.  `systemctl daemon-reload`
2.  `systemctl restart xray`
3.  `systemctl restart nginx`
4.  `systemctl status xray`
5.  `systemctl status nginx`

---

for debian

1.  `apt update && apt upgrade -y`
2.  `apt install curl wget unzip git socat fail2ban -y`
3.  `cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local`
4.  `apt install unattended-upgrades apt-listI'm sorry, but the text you provided appears to be incomplete. It seems to be a tutorial for building a VLESS-XTLS-uTLS-REALITY protocol with Xray-core on Debian 11, but it ends abruptly with step 4 of the Debian installation process. If you have any specific questions or need further assistance, please provide more information or context so that I can better understand what you need help with.
