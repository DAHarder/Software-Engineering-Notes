# Common Commands
## `show dbs`
List all available databases.

## `use <db_name>`
Switch to the database named `<db_name>`.

## `db.createCollection("<collection_name>")`
Create a new collection with the specified name.

## `show collections`
List all the collections in the current database.

## `db.<collection_name>.insert(<document>)`
Insert a new document into a specified collection.

## `db.<collection_name>.insertMany(<documents_array>)`
Insert multiple documents into a specified collection.

## `db.<collection_name>.find()`
Retrieve all documents from a specified collection.

## `db.<collection_name>.findOne()`
Retrieve the first document from a specified collection.

## `db.<collection_name>.find(<query>)`
Query documents based on specific conditions in a collection.

## `db.<collection_name>.update(<query>, <update>, <options>)`
Update documents based on query conditions.

## `db.<collection_name>.replaceOne(<filter>, <replacement>, <options>)`
Replace one document matching the filter.

## `db.<collection_name>.updateOne(<query>, <update>, <options>)`
Update the first document matching the query conditions.

## `db.<collection_name>.updateMany(<query>, <update>, <options>)`
Update all documents matching the query conditions.

## `db.<collection_name>.deleteOne(<query>, <options>)`
Delete the first document matching the query conditions.

## `db.<collection_name>.deleteMany(<query>, <options>)`
Delete all documents matching the query conditions.

## `db.<collection_name>.drop()`
Drop a specified collection.

## `db.<collection_name>.count(<query>)`
Count the number of documents matching the query conditions.

## `db.<collection_name>.aggregate(<pipeline>)

Perform aggregation operations using different stages, like `$match`, `$group`, `$sort`, etc.

## `db.<collection_name>.createIndex(<keys>, <options>)`
Create an index on the specified keys.

## `db.<collection_name>.dropIndex(<index_name>)`
Drop an index by its name.

## `db.<collection_name>.getIndexes()`
Retrieve a list of indexes that exist for the collection.

## `db.<collection_name>.renameCollection("<new_collection_name>")`
Rename collection to the specified new name.