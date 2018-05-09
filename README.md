# server
Main public server initialization, setup ve maintenance directives.

[TOC] 

## Platform 
1 GB Memory / 25 GB Disk / FRA1 - Ubuntu 18.04 x64

## Initialization
### Firewall
```
sudo ufw enable
sudo ufw allow http
sudo ufw allow OpenSSH
#  Other service ports 3004, ....
```

### Directory structure
- applications
  - app1
- downloads
  - file1
- services
  - serv1
  
## Setup

### Node.js installation
```
# You can change nvm version
curl -sL https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh -o install_nvm.sh
bash install_nvm.sh
source ~/.profile
# You can change node.js version
nvm install 8.11.1
```
#### Global modules
- pm2
```
npm install -g pm2
pm2 startup systemd
```
- bower
```
npm install -g bower
```

### Anaconda Python installation
[How To Install the Anaconda Python Distribution on Ubuntu 16.04](https://www.digitalocean.com/community/tutorials/how-to-install-the-anaconda-python-distribution-on-ubuntu-16-04)
```
curl -O https://repo.continuum.io/archive/Anaconda3-5.1.0-Linux-x86_64.sh
bash Anaconda3-5.1.0-Linux-x86_64.sh
source ~/.bashrc
```

### MongoDB installation
[Install MongoDB Community Edition on Ubuntu](https://docs.mongodb.com/manual/tutorial/install-mongodb-on-ubuntu)
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu xenial/mongodb-org/3.6 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list
sudo apt-get update
sudo apt-get install -y mongodb-org
sudo service mongod start
```
