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

### Python 3 installation
```
sudo apt-get install -y python3-pip
sudo apt-get install build-essential libssl-dev libffi-dev python-dev
sudo apt-get install -y python3-venv
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
