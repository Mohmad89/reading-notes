# LinkedList And Big O

## 1. Big O :
Big O(oh) notation is used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors :     
1. Running Time : The abount of time a function needs to complete.  
2. Memory Space : The amount of memory resources a function uses to store data and instructions      
## The Key Areas for analysis : 
### 1. Input Size :   
regers to the size of the parameter values that are read by the algorithm.    
we will use th letter (n) to refer to the input Size value .  
### 2. Units of Measurement :   
To evaluate a function for Time and Space complexity 
### 3. Orders of Growth 
As the value of (n) grows, the Order of Growth represents the increase in Running Time or Memory Space .
### 4. Best Case, Worst Case, and Average Case.
___ 
## 2. LinkedLists 
### What is a Linked List ? 
A Linked List is a sequence of Ndes that are connected/ linked to each other. The most defining feature of a Linked List is that each Nide references the next Node in the link.    
### There's  two type from linked list 
1. Singly   
 Singly refers to the number of references the node has. A Singly linked list means that there is only one reference, and the reference points to the Next node in a linked list.  
 2. Doubly    

Doubly refers to there being two (double) references within the node. A Doubly linked list means that there is a reference to both the Next and Previous node.
### Linked list components :   

1. Linked List - A data structure that contains nodes that links/points to the next node in the list.  
2. Node - Nodes are the individual items/links that live in a linked list. Each node contains the data for each link.  
3. Next - Each node contains a property called Next. This property contains the reference to the next node.  
4. Head - The Head is a reference of type Node to the first node in a linked list.    
5. Current - The Current is a reference of type Node to the node that is currently being looked at. When traversing, you create a new Current variable at the Head to guarantee you are starting from the beginning of the linked list.   



