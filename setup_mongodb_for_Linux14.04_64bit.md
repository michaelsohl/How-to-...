## Setup mongodb for Linux 14.0
In this tutorial mongodb is installed, set up, and launched in simple example.

#### Importing the Key
GPG keys of the software distributor are required by the Ubuntu package manager 
apt (Advanced Package Tool) to ensure package consistency and authenticity. 
Run this command to import MongoDB keys to your server.
```
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 7F0CEB10
```
#### Create source list file MongoDB
Create a MongoDB list file in /etc/apt/sources.list.d/ with this command:

```
echo "deb http://repo.mongodb.org/apt/ubuntu "$(lsb_release -sc)"/mongodb-org/3.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.0.list
```
then update the repo
```
sudo apt-get update
```

#### Install MongoDB
Now you can install MongoDB typing this command:
```
sudo apt-get install -y mongodb-org
```

## Configure MongoDB with username and password

#### Open mongo shell
```
mongo
```
Incase you recieved an error like this: Failed global initialization: BadValue Invalid or no user locale set. Set:
```
export LC_ALL=C
mongo
```

#### Switch to database admin 
Once you are in the shell run:
```
use admin
```

#### Create root user (Did not need to??)
Create root user with this command:
```
db.createUser({user:"admin", pwd:"admin123", roles:[{role:"root", db:"admin"}]})
```

#### Make database accessible from port
Create a database directory
```
sudo mkdir /data/db
```
Then run:
```
sudo mongod --pathdb /data/db
```

#### Create Database
You are now in mongodb shell
Enter:
```
use NAME_OF_DATABASE
```











