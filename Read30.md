# Hash Table

### Hashtables are a data structure that utilize key value pairs. This means every Node or Bucket has both a key, and a value.

* Hash - A hash is the result of some algorithm taking an incoming string and converting it into a value that could be used for either security or some other purpose. In the case of a hashtable, it is used to determine the index of the array.
* Buckets - A bucket is what is contained in each index of the array of the hashtable.
* Collisions - A collision is what happens when more than one key gets hashed to the same location of the hashtable.

## Why do we use them?

1. Hold unique values
2. Dictionary
3. Library

* A hash is the ability to encode the key that will eventually map to a specific location in the data structure that we can look at directly to retrieve the value.

## Example 

* ["Greenwood:98103", "Downtown:98101", "Alki Beach:98116", "Bainbridge Island:98110", ..]  
    If we want to find any zip Code with use hash function . we will call hash function that this function tack aky and return Integer number this integer number is like index for evry key inside the array the big O for this proccess is O(1).
    
# Structure 

## Hashing 

* a hash code turns a key into an integer 

## Creating a Hash 

1. A hashtable traditionally is created from an array.
2. turn the key into numiric value.
3. multibley it by a prime number such 599.
4. use modulo to get the remainger of the result.
5. insert into the array at that index .

## Collisions

* A collision occurs when more than one key hashes to the same index in an array.


* to aboid Collisions Hash map do this to store values 
    1. accept a key
    2. calculate the hash of the key
    3. use modulus to convert the hash into an array index
    4. store the key with the value by appending both to the end of a linked list
* Hash maps do this to read value:
    1. accept a key
    2. calculate the hash of the key
    3. use modulus to convert the hash into an array index
    4. use the array index to access the short LinkedList representing a bucket
    5. search through the bucket looking for a node with a key/value pair that matches the key you were given

## Internal Method

1. Add () : When adding a new key/value pair to a hashtable
    1. send the key to the GetHash method.
    2. Once you determine the index of where it should be placed, go to that index
    3. Check if something exists at that index already, if it doesn’t, add it with the key/value pair.
    4. If something does exist, add the new key/value pair to the data structure within that bucket.
2. Find () :  
   * The Find takes in a key, gets the Hash, and goes to the index location specified.
3. Contains() : 
    * The Contains method will accept a key, and return a boolean value
4. GetHash () :
    *  will accept a key as a string, conduct the hash, and then return the index of the array where the key/value should be placed.
___
