## 1. **How can we chnage the permission for a file under Linux ?**

* To change the permissions of a file in Linux, use the `chmod` command. For example, if you have a file called `example.txt` and you went to give read and write permissions to others, you would use:

```bash
chmod 640 example.txt
```

## 2. **How can we list the partitions in linux ?**

* To list the partitions in linux, you can use the `lsblk` or `fdisk -l` commands, For instance:

```bash
lsblk
```
or

```bash
sudo fdisk -l
```
* this is useful when setting up a new disk or troubleshooting storage issues on your server.

## 3. **what is the command to find the current load average in the system ? **

* The `uptime` or `top` commands can be used to find the current load average:

```bash
uptime
```
or 

```bash
top
```

## 4. how to check all the running processes ?

* to check all the running processes, use the `ps` command with the `aux` options

```bash
ps -aux
```

or 

```bash
top
```

## 5. what is a workspace in jenkins ?
