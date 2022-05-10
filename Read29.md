# Room API

## Save datain a local database using Room 

* The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite

* Benefits for Room library :  
    1. Compile-time verification of SQL queries.
    2. Convenience annotations 
    3. Streamlined database migration paths.

## Setup to use Romm in your App 
1. add Room dependencies inside build.gradle
2. Primary components
    1. database Class
    2. data entities for every table
    3. Data access objects (@Dao)for queries retrieve data from the datavase as instance of the assosciated data entity objects.

# Defining data using Room entities 

* when we use the Room persistence library to store your app's data , we must to define entity corresponds to a table in the associated Room database
* we use @Entity notation before any class to assign it as table inside database , and we must assign the primaryKey for this table 
* we can use tableName properites to change the table name and @ColumnInfo to change the column name 

## Support full-text search

if your app requires very quick access to database information through full-text search (FTS), have your entities backed by a virtual table that uses either the FTS3 or FTS4

# Define Relationshi8ps between objects 

## There are two way to define and query a relationship between entities : 

1. Intermediate data class : 
    create class and then create @Dao interface to the queries
2. Multible reutn types :  
    in this approach we don't need to crete another class Instead, you define a multimap return type for your method based on the map structure that you want and define the relationship between your entities directly in your SQL query

## Define one-to-one Relationship

* A one-to-one relationship between two entities is a relationship where each instance of the parent entity corresponds to exactly one instance of the child entity, and vice-versa.
* we use @Relation notation and parentColumn and entityColumn propirites to do one-to-one Rlationship

## Define one-to-many relationships

* A one-to-many relationship between two entities is a relationship where each instance of the parent entity corresponds to zero or more instances of the child entity, but each instance of the child entity can only correspond to exactly one instance of the parent entity.

* we use @Relation notation and parentColumn and entityColumn propirites
and create List variable for many instance

## Define many-to-many relationships

* A many-to-many relationship between two entities is a relationship where each instance of the parent entity corresponds to zero or more instances of the child entity, and vice-versa

* we use @Relation notation and parentColumn and entityColumn propirites
and create List variable for many instance and we must add associateBy properites to the Relation notation

## Define nested relationships

* Sometimes, you might need to query a set of three or more tables that are all related to each other. In that case, you would define nested relationships between the tables.

___