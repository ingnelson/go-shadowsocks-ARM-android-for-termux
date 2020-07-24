# go-shadowsocks-ARM-android-for-termux
go-shadowsocks2 binary for ARM (android)
This is a fork of :
https://github.com/shadowsocks/go-shadowsocks2

*First check that go-shadowsocks2 is install in your VPS 
*cd /etc/systemd/system/shadowsocks2.service

should be inside somthing like this :

[Unit]
Description=Next-generation Shadowsocks in Go

[Service]
EnvironmentFile=/etc/default/shadowsocks2
ExecStart=/usr/local/bin/shadowsocks2 $OPTIONS
Restart=always
KillMode=process
TimeoutStartSec=5
TimeoutStopSec=5

[Install]
WantedBy=default.target

===============================
then use this commands 
systemctl daemon-reload
systemctl start shadowsocks2.service
systemctl status shadowsocks2


*example How to run go-shadowsocks on Termux:
First download the file with the command = wget
then = chmod +x shadowsocks2
run shadowsocks2 with the command = ./shadowsocks2 -c 'ss://AEAD_CHACHA20_POLY1305:Gosixee7@174.135.12.233:80' -socks :1080 -verbose -plugin ./httpierce &>> ss.log &
test the connection = curl --socks5h://127.0.0.1:1080 http://httpbin.org/ip



