# MongoDB-BasicTopics
This is my personal repo to learn the basic topics of MongoDb and how to intall MongoDB Server

Video Link: https://www.youtube.com/watch?v=lWMemPN9t6Q

# Instalation

* I defuse the "Install MongoD as a Service"

* After the instalation we need to add the application to the Environment Variables PATH:
    - To see the version in the same folder with PowerShell: 
        -- .\mongod --version

* Now we can write the command in CMD to see MongoDb version
-- mongod --version

* Create a "data" Folder in "C:" and then create a "db" foler in "data" folder.

# Run MongoDb Data Base

* Run command to stay executed MongoDb Server:
-- mongod 

* Wait for the message that give us the port wher MongoDb is executing

* Tipe "Ctrl" + "C" to finish


# Run Mongo Application (MongoDb Shell Version 6 - )

* Run command in other CMD to executed MongoDb:
-- mongo

* Click Enter in the CMD where is running MongoDb Data Base

* Tipe "exit" to exit from Mongo Application

# Run Mongosh (MongoDb Shell Version 6 + )

* You need to download mongosh from:
https://www.mongodb.com/docs/mongodb-shell/install/

* Run command:
-- mongosh
Instead of mongo


# MongoDb Scheme

* Data Base
Collection set

* Colections
Are a set of documents (objects) with their own data

This colection is saved in JSON files

* Documents
Objects with their own data


# Commands

* -- help
Show help menu

* -- db
Show the Database that i'm using
By default you will be in DataBase "test"

* -- show dbs
Show the Databases for MongoDb inner using
1.- admin
2.- config
3.- local

These three Databses are used to store Users, Permissions mainly

* -- show collections
Show the Collections from the current DataBase

* Create a Database
-- use database_name

After insert the first colection to the database it will be created

* Create a Collection

--db.createCollection("collection_name")

* Create a Collection and Insert data at same time

-- db.collection_name.insert({"name": "laptop"})

* Remove a Collection
-- db.collection_name.drop()

* Delete a Database
-- db.dropDatabase()

It's going to delete the current Database, so it's importat to verify with the command -- db thata we are in the correct Datanase