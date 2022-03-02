# Object Orianted Programming (OOP)  
## What Is an Object ? 
An object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life. 
___
 ## What is the class ? 
 A class is a blueprint or prototype from which objects are created.    
Ex :  {    class car { 7
    // properites 
    String type = "";  
    String color = "";

    //constructor  
    public car (String type, String color){
        this color = color;
        this type = type;
    }  
    // method  
    public void setColor (String color){
        this.color = color;
    }
    public void getColor (){
        return this.color;
    }
}

___

## What is the Inheritance ?
This section explains how classes inherit state and behavior from their superclasses, and explains how to derive one class from another using the simple syntax provided by the Java programming language.
 Ex :  
    class MountainBike extends Bicycle {

    // new fields and methods defining 
    // a mountain bike would go here

}

___

## What is the Interface ? 
=> An interface is a contract between a class and the outside world.   
=> In its most common form, an interface is a group of related methods    with empty bodies
Ex :   
nterface Bicycle {

    //  method with empty body
    void changeCadence(int newValue);

    void changeGear(int newValue);

    void speedUp(int increment);

    void applyBrakes(int decrement);
}
___

## What is the Package ?
A package is a namespace for organizing classes and interfaces in a logical manner. Placing your code into packages makes large software projects easier to manage

___
## Binary, Decimal and Hexadecimal Numbers

### 1. Binary Number (Base 2)
is that contain from tow digets (0 , 1 )  
Ex :  
10 => 2   
11 => 3   
### 2. Decimal Number  (Base 10)
Every digit in a decimal number has a "position", and the decimal point helps us to know which position is  
Ex :  
17.82  
### 3.Hexadecimal Numbers   (Base 16)
Ex:  
0 => 0  
1 => 1  
.  
.  
.
9  => 9  
10 => A   
11 => B    
.  
.  
.  
15 => F  

___