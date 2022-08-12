# Linux

## Useful links

[Linux man page](https://linux.die.net/man/)

[How to check file and directory size in Linux](https://www.simplified.guide/linux/file-folder-size-check)

[Linux nohup command](https://www.computerhope.com/unix/unohup.htm)

### Useful Commands

 ```bash
 # Check folder size
 find -type d -name '[!.]*' -exec du -sh {} + | sort -h
```

### Manage processes

[How to check running process in Linux using command line](https://www.cyberciti.biz/faq/how-to-check-running-process-in-linux-using-command-line/)

```bash
ps -auxww

sudo ps -a

ps -A

ps aux | grep git

sudo ps aux | grep vim
```

### sudo-apt

[What does “sudo apt-get update” do?](https://askubuntu.com/questions/222348/what-does-sudo-apt-get-update-do)

```bash
sudo apt-get update

sudo apt-get upgrade

sudo apt-get dist-upgrade

sudo reboot
```

### Check os version in Linux

```bash

# /etc/os-release file
cat /etc/os-release

# The lsb_release command gives LSB (Linux Standard Base) and distribution-specific information on the CLI
lsb_release -a

# Use hostnamectl command to query and change the system hostname and related settings
hostnamectl

# uname command prints the Linux kernelk version
uname -r

# /proc/version
cat /proc/version

# /etc/issue file
cat /etc/issue file

# You can also view the manual page on uname using the following command:
man hostnamectl
man uname
man cat
```

### Network

[How to: Running a TCP Traceroute](https://support.opendns.com/hc/en-us/articles/227989007-How-to-Running-a-TCP-Traceroute)

```bash
tcptraceroute <host> <port>
```

### chown

How to user chown

```bash
chown [OPTIONS] USER[:GROUP] FILE(s)
```

How to Change the Owner of a File

```bash
chown USER FILE
```

How to Change the Owner and Group of a File

```bash
chown USER:GROUP FILE
```

How to Change the Group of a File

```bash
chown :GROUP FILE
```

### tcpdump

[tcpdump examples](https://hackertarget.com/tcpdump-examples/)

```bash
sudo tcpdump -i eth0 host 10.10.1.1

sudo tcpdump -i -v eth0 host my.jenkins.master.server.net
```

### Tar (tarball - collection of files placed into a highly compressed archive)

```bash
# download the tarball to the server
curl -k -O https://server.company.net/some-folder/name-of-the-compressed-file.tgz

# list the archive/zip to check that everything is ok
tar ztf <name-of-the-compressed-file.tgz>

# unpack the archive  
tar zxf <name-of-the-compressed-file.tgz>

# unpack to a specific folder
tar zxf file.tar --directory /path/to/directory
```

### Run bash as super user

```bash
sudo su -

# do your work and exit
```

### Run bash as a specific user that exists

```bash
sudo su - <the user>

# do your work and exit
```

### Is systemd-resolved.service — Network Name Resolution manager up and running

https://www.freedesktop.org/software/systemd/man/systemd-resolved.service.html

```bash
# Check status:
sudo systemctl status systemd-resolved.service

# Got this message:
Warning: journal has been rotated since unit was started, output may be incomplete.

# Restart service:
sudo systemctl restart systemd-resolved.service
```
