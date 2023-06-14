# MongoDB-BasicTopics
This is my personal repo to learn the basic topics of MongoDb and how to intall MongoDB Server.

Transform the JSON files to BSON files

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

* Create Multiple Collections
-- db.collection_name.insert([{"name": "laptop"},{"name": "mouse", "quantity": 15}, {"name": "monitor"}])

* Remove a Collection
-- db.collection_name.drop()

* Delete a Database
-- db.dropDatabase()

It's going to delete the current Database, so it's importat to verify with the command -- db thata we are in the correct Datanase

* Search all the data of a Collection
-- db.collection_name.find()

* Search a specific data from collection 
-- db.collection_name.find({"property":"property_name"})

Also we can do with two or more properties
-- db.collection_name.find({"property":"property_name", "property2":"property_name2"})

With finOne() it will only return the first data to match
-- db.collection_name.findOne({"property":"property_name", "property2":"property_name2"})

Show only some properties from the data (1 => show and 0 => Not to show )
-- db.collection_name.findOne({"property":"property_name", "property2":"property_name2"}, {"property":1, "property2": 1, "_id":0})

* Show the data organized by one property
-- db.collection_name.find({"property":"property_name"}).sort({property: 1})

* Show only certain number of data
-- db.collection_name.find().limit(2)

* Show the number of data in a collection
-- db.collection_name.count()


# Methods with Collections

* forEach()
-- db.collection_name.find().forEach(() => print())

Example :
    db.products.find().forEach(product => print("Product Name: " + product.name))
(Prints the name of each product of collection "products" )


* .update() with $set and upsert:true
-- db.collection_name.update({"propertyToSearch":"property_name"}, {$set: {"newProperty":"newProperty_name"} })

Examples:
Adding 1 new property that doesn't exist
    db.collection_name.update({"name": "keyboard"}, {$set: {"price":99.99} })

Modifying the value of 2 properties
    db.collection_name.update({"name": "keyboard"}, {$set: {"name": "monitor", "price":99.99} })

Adding a new object that doesn't exist to the collection
    db.collection_name.update({"name": "desktop"} {$set: {"description": "Gaming Desktop"} }, {upsert:true})

Increment the value of a property from project
    db.collection_name.update({"name": "mouse"}, {$inc: {"price": 1.01}})

(Replace or add the information of the first object with the info of the second Parameter this property ("propertyToSearch") with all the objects of the second parameter ("newProperty")(Could be one or more properties))

(upsert:true -> The object don't exist, so add it)

($set: -> If the property exist, it will be replaced, if not, it will be added)

($inc: -> Increment numeric values)