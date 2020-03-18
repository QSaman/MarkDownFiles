# Mounting a Samba directory
 
```
mount -t cifs //SERVER/sharename /mnt/mountpoint -o username=username
```

Since you need to mount using `sudo`, it's likely you don't have write permission as a normal user. You can use 

```
mount -t cifs //SERVER/sharename /mnt/mountpoint -o uid=$(id -u),gid=$(id -g),username=username
```
