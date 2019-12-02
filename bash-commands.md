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

### SSH from a bash prompt to a remote server (Secure SHell)

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
ps -aux

sudo ps -a

ps -A

ps aux | grep git

sudo ps aux | grep vim

```
