start sshd
```
systemctl start sshd
```
get ip
```
ip a
```

send file with scp
```
scp /file/path user@ip:/path/to/send
```

or rsync

stop sshd
```
sudo systemctl stop sshd
```

stop autostart
```
sudo systemctl disable ssh
```