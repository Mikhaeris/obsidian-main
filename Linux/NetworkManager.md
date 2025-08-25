First install "networkmanager"
For GUI tool: "nm-connection-editor"
For applet: "network-manager-applet"

How to startup mobile hotspot:
Need to install: "dnsmasq"

For android 10 or older need to set:
/etc/NetworkManager/system-conections/$WIFI_NAME.nmconnection

add in \[wifi -security\] this "pmf=1"
Like this:
```
[wifi-security]
key-mgmt=wpa-psk
pmf=1
psk=blahblah123
```

Resources:
https://wiki.archlinux.org/title/NetworkManager
https://askubuntu.com/questions/1421747/wifi-hotspot-from-ubuntu-22-04-not-visible-on-android-12-0