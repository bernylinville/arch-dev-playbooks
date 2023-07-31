# Some Custom Steps

x11vnc

```bash
x11vnc -storepasswd
```

ssh key

```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

gpg key

`export GPG_TTY=$(tty)`

```bash
gpg --full-generate-key
gpg -K --keyid-format=long
gpg --armor --export <key>
git config --global user.signingkey <key>
git config --global commit.gpgsign true
```

across gfw
```bash
# clash.meta
wget https://github.com/MetaCubeX/Clash.Meta/releases/download/v1.15.0/clash.meta-linux-amd64-v1.15.0.gz
gzip -d clash.meta-linux-amd64-v1.15.0.gz
sudo install clash.meta-linux-amd64-v1.15.0 /usr/local/bin/clash
sudo mkdir /etc/clash
```

```conf
# /etc/systemd/system/clash.service
[Unit]
Description=Clash-Meta Daemon, Another Clash Kernel.
After=network.target NetworkManager.service systemd-networkd.service iwd.service

[Service]
Type=simple
User=root
Group=root
LimitNPROC=500
LimitNOFILE=1000000
CapabilityBoundingSet=CAP_NET_ADMIN CAP_NET_RAW CAP_NET_BIND_SERVICE
AmbientCapabilities=CAP_NET_ADMIN CAP_NET_RAW CAP_NET_BIND_SERVICE
Restart=always
ExecStartPre=/usr/bin/sleep 1s
ExecStart=/usr/local/bin/clash -d /etc/clash

[Install]
WantedBy=multi-user.target
```

