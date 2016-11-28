## Bash

#### Ssh
```bash
ssh -i ~/.ssh/key root@127.0.0.1 # ssh into a root server with that ip and that key
ssh-keygen -t rsa -C "your_email@example.com" # generate a new ssh key
ssh <host> # if ~/.ssg/config is setup
```

#### System
```bash
free -m # check free memory on linux system
df # check free disk space
```

#### Scripts
```bash
sudo chmod +x .
sudo chmod 755 filename
```

#### Directory, Files & Transfer
```bash
chmod 755 filename # change permission
chown -R <user> <directory> # give directory to user
ll <directory> # see permission
rsync -r -av --progress <source> <dest>
```
