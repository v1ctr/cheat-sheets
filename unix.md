# UNIX / Linux Cheat Sheet

## List Current Logged In Users
```
who
```
or
```
w
```

## Find out who you are currently Logged In
```
whoami
```
or
```
id
```

## Create a new group
```
groupadd -g <group-id> <group-name>
```
## set groups for member
```
usermod -G <group-name>,<group-name> <user-name>
```
## add group for member
```
usermod -aG <group-name> <user-name>
```
## display who is a member of a group
```
getent group <group-name>
```

## Permissions
Give read, write, and execute to everyone.
```
chmod ugo+rwx <foldername>
```

## firewalld
### Start firewalld 
```
firewall-cmd --state
systemctl start firewalld
firewall-cmd --state
```