# Bash

## Commands

### Usefull Links

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
ls -alh
```

### Find

```bash
find . -name *.img
```

### Copy

```bash
# Copy folder recursive
cp -R myfolder mynewfolder

# Copy Folder recursive and preserver original permissions
cp -rp myfolder mynewfolder

# Copy file and preserver original permissions
co -p myfile.txt mynewfile.txt

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

### Name Server Lookup

```bash
nslookup <server.company.net>
nslookup <server>
nslookup <ip>
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

### Get Proxy

```bash
env  | grep  -i proxy
```
