# MongoDB and Rust Basic
## Installation
[Official WSL installation](https://docs.microsoft.com/en-us/windows/wsl/tutorials/wsl-database)

Create a directory (For sake of explaination, call this directory `.../dbDir`). This is where the database is going to be stored.

Run `chmod o+w -R .../dbDir` to grant write permission to MongoDB

Run `mongod --dbpath .../dbDir` to start database

Run `mongo` in separate terminal to access **mongodb shell**, which allows to make database query in terminal

> This installation require `sudo` which we may not want, [this article](https://dev.to/seanwelshbrown/installing-mongodb-on-windows-subsystem-for-linux-wsl-2-19m9) may help

## Access Control
Follow [this link](https://docs.mongodb.com/manual/tutorial/configure-scram-client-authentication/) for activating access control\
Follow [this link](https://docs.mongodb.com/manual/reference/method/db.updateUser/) for editing permission for user

## Rust Access
Official site's code
* [From GitHub](https://github.com/mongodb/mongo-rust-driver) 
* [From MongoDB docs](https://docs.mongodb.com/drivers/rust/) 
should be usable without much issue

If the database is created like default, the connection will be hosted on **port 27017**, and the connection string will be `"mongodb://localhost:27017"`

For databases with access control, use connection string `"mongodb://username:password@localhost:27017"`

## Quirks
* MongoDB does not have authentication by default, [this SO article](https://stackoverflow.com/questions/38921414/mongodb-what-are-the-default-user-and-password) shows what can be done to add "access control"
