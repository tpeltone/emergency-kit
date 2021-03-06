# Bash

## Commands

### Usefull Links

[Linux nohup command](https://www.computerhope.com/unix/unohup.htm)

### Create a folder

```bash
mkdir myfolder
```

### Change directory

```bash
cd myfolder
```

### List files and folders

```bash
ls -a
ls -l
ls -F
ls -laF
ls -f (aF)
```

### Find

```bash
find . -name *.img
```

### SSH from a bash prompt to a remote server (Secure Shell)

```bash
# Generate SSH key
ssh-keygen -t rsa -b 2048

# Copy SSH public key to host authorized_keys
ssh-copy-id -i ~/.ssh/mykey user@host

# Test the copied key
ssh -i ~/.ssh/mykey user@host

# ssh to host
ssh host

# as a specific user
ssh user-name@host

# as a specific user with password
ssh user-name@host
```

### Create .ssh folder and keys manually and set the prefered permissions

```bash
# The .ssh directory permissions should be chmod 700 (drwx------)
mkdir .ssh;chmod 700 .ssh

cd .shh

# The public key file permissions should be chmod 644 (-rw-r--r--)
vim id_rsa.pub;chmod 644 id_rsa.pub

# The private key file permissions should be chmod 600 (-rw-------)
vim id_rsa;chmod 600 id_rsa
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

### Name Server Lookup

```bash
nslookup <server.company.net>
nslookup <server>
nslookup <ip>
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

### cat

```bash
# reads files sequentially and writes the content to standard output
cat /folder1/folder2/file.crt

# multiple files
cat /folder1/folder2/file1.crt /folder1/folder2/file.key

# all files in folder
cat *

# create a new file of the content

cat /folder1/folder2/file1.crt /folder1/folder2/file.key > certificates.pem
```

### mv

```bash
# moves one or more files or directories from one place to another
mv /folder1/file.csr /folder2/folder3/

```

### curl
 
```bash
curl -k -v https://my-server.net

curl -k -v https://my-server.net:5000

curl http://my-server.net
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

### sudo-apt

[What does “sudo apt-get update” do?](https://askubuntu.com/questions/222348/what-does-sudo-apt-get-update-do)

```bash
sudo apt-get update

sudo apt-get upgrade

sudo apt-get dist-upgrade

sudo reboot
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

### Get Proxy

```bash
env  | grep  -i proxy
```

### Network

[How to: Running a TCP Traceroute](https://support.opendns.com/hc/en-us/articles/227989007-How-to-Running-a-TCP-Traceroute)

```bash
tcptraceroute <host> <port>
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
