Create a Ubuntu VM with Ubuntu 18.04.
```
sudo apt-get update
sudo apt-get upgrade
sudo apt install curl
```
Install npm
```
curl -sL https://deb.nodesource.com/setup_12.x | sudo -E bash -
sudo apt-get install nodejs
```
Install mongo DB
```
sudo apt update
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 9DA31620334BD75D9DCB49F368818C72E52529D4
echo "deb [ arch=amd64 ] https://repo.mongodb.org/apt/ubuntu bionic/mongodb-org/4.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.0.list
sudo apt update
sudo apt install mongodb-org -y
```

https://docs.mongodb.com/manual/tutorial/deploy-replica-set-for-testing/

Mongo DB conf:
```
rsconf = {
  _id: "rs0",
  members: [
    {
     _id: 0,
     host: "192.168.100.10:27017"
    },
    {
     _id: 1,
     host: "192.168.100.10:27018"
    },
    {
     _id: 2,
     host: "192.168.100.10:27019"
    }
   ]
}
```
Initiate Mongo conf:
```
rs.initiate( rsconf )
```


Setup Redis
```
wget http://download.redis.io/releases/redis-5.0.5.tar.gz
tar xzf redis-5.0.5.tar.gz
cd redis-5.0.5
make
# start redis server
src/redis-server
```

Install mail-catcher
```
sudo apt install ruby ruby-dev
   99  sudo gem install mailcatcher
  100  sudo apt-get install libsqlite3-dev
  101  sudo gem install mailcatcher
```

