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

## add sudo user 
```
adduser username
passwd username
usermod -aG wheel username
```
Use the ```usermod``` command to add the user to the wheel group.
By default, on CentOS, members of the wheel group have sudo privileges.

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
Recursively Change the File's Permissions
```
chmod -R MODE DIRECTORY
```

## firewalld
### Start firewalld 
```
firewall-cmd --state
systemctl start firewalld
firewall-cmd --state
```

