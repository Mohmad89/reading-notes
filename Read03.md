# Java Type System  
## 1) Fold Type 
 * int  
 * float
 *  boolean
 * double  
 * short 
## 2) Reference Type (Object) 
* Integer 
* Boolean 
* Double  
* Float 
## Autoboxing proccess 
Is convert a primitive type to a reference type  
Ex :      
 Integer j = 1;
## Unboxing proccess 
Is convert a reference type to a primitive type    
int i = new Integer(1);  

___
# Exeptions 

## defenition :
An exception is an event that occurs during the execution of a program that disrupts the normal flow of instructions . 

### usually this exception happend inside method 
## How we can Avoid this exception ? 
1. Whith use try to catch the exceptio  exception
2. or whith add the method for this exception
## Kind of exception : 
1. checked exception  :   
when we want to reade from afile we need to add (java.io.FileNotFoundException) or whith use try .
2. Error  
is Inability to read specific file because there is wrong in hardware or system malfunction. 
3. Runtime exception :  
These usually indicate programming bugs, such as logic errors or improper use of an API.
___  
# How we can throw these exceptions?  
## with use throw stetments 
Ex :  
public Object pop() {  
    Object obj;  
  
    if (size == 0) {  
        throw new EmptyStackException();  
    }  

    obj = objectAt(size - 1);  
    setObjectAt(size - 1, null);  
    size--;  
    return obj;  
}  
__ 

# Advantages of Exceptions

## 1. Separating Error-Handling Code from "Regular" Code
Exceptions enable you to write the main flow of your code and to deal with the exceptional cases elsewhere

## 2. Propagating Errors Up the Call Stack
 is the ability to propagate error reporting up the call stack of methods

## 3. Grouping and Differentiating Error Types
