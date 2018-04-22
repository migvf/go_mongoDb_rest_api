# Simple GOLANG API Rest

This project shows an easy API Rest built in GO language, which stores data in Mongo DB (CRUD operations with movies).

## Getting started

This section will help you to understand what is needed to use this project (or to understand how to create a similar one).

### Prerequisites 

First of all, we need GOLANG and Mongo DB installed in our machine:

1. GOLANG installation: You can follow the instructions from [GOLANG Web](https://golang.org/doc/install). Summary for linux users:
    * [Download the archive](https://golang.org/dl/) and extract it into /usr/local. Example: **tar -C /usr/local -xzf go$VERSION.$OS-$ARCH.tar.gz**
    * Add /usr/local/go/bin to PATH environment variable. It is better to add this instruction to .bashrc file and not directly in the terminal (every time we open the terminal, our PATH variable will have added the GO Path). Therefore,you have to add to .bashrc this line: **export PATH=$PATH:/usr/local/go/bin**
2. Mongo DB installation, for linux (Debian) users:
    * Import the public key used by the package management system: **sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5**
    * Create a /etc/apt/sources.list.d/mongodb-org-3.6.list file for MongoDB.For Debian 8: **echo "deb http://repo.mongodb.org/apt/debian jessie/mongodb-org/3.6 main" | sudo tee /etc/apt/sources.list.d/mongodb-org-3.6.list**
    * Reload local package database: **sudo apt-get update**
    * Install the MongoDB packages: **sudo apt-get install -y mongodb-org**
    * Start Mongo DB: **sudo service mongod start**

### Needed libraries

* **toml**: Parse the configuration file (MongoDB server & credentials)
* **mux**: Request router and dispatcher for matching incoming requests to their respective handler
* **mgo**: MongoDB driver
```
go get github.com/BurntSushi/toml gopkg.in/mgo.v2 github.com/gorilla/mux
```

### Testing
For testing your API rest you need to have your Mongo DB started and then run the app: **go run app.go**. After that you can use several tools for testing the endpoints. I have used SOAP UI, but you can use Postman or simply the curl command.