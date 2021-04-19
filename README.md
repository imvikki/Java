#Java

Lamda : Assigning a function to a variable.

why lambda ?
 - it enables functional programming
 - readable and concise code (eliminate boiler-plate code)
 - enables support for parallel processing
 
The return type of lamda is interface with single abstract method (SAM).
Lamda replaces anonymous inner class.

s -> s.length()
here we are not specifying s is of what type. The JVM is smart enough to take the type from interface. This is type inference.
 
Functional vs object oriented programming
  Java is a object oriented programming, we use functional way when needed. Functional programming makes code much readable and maintain.
  
this reference :
	In anonymous inner class, this is the reference of the inner class.
	In lambda, this is the reference of the outer class.
	
Streams : 
	- It is one of the feature of java 8.
	- It is not a collection. It doesn't store values. It doesn't change the values. 
	  If you want the result, you can get it by using functions (eg. Count()).
	
Collections :

ArrayList (List) : 

	- It’s a very good alternative of traditional java arrays.
	- ArrayList is a resizable-array implementation of the List interface.
	- ArrayList grow by half of its size
	- ArrayList can dynamically grow and shrink after addition and removal of elements.
	- An ArrayList class can act as a list only because it implements List only.
	
	- Manipulation with ArrayList is slow because it internally uses an array. If any element is removed from the array, all the bits are shifted in memory.
	- ArrayList is better for storing and accessing data.
	
	- It maintains insertion order.
	- It allows duplicate and null values.
	- easy and fast in searching.
	
LinkedList (List and Dequeue) : 

	- LinkedList class can act as a list and queue both because it implements List and Deque interfaces.
	
	- Manipulation(insertion and deletion) with LinkedList is faster than ArrayList because it uses a doubly linked list, so no bit shifting is required in memory.
	- LinkedList is better for manipulating data.
	
	- It maintains insertion order.	
	- It allows duplicate and null values.
	
Vector (List) (Threadsafe) : 

	- Vector is synchronized. This means if one thread is working on Vector, no other thread can get a hold of it.
	- The vector was not the part of collection framework, it has been included in collections later. It can be considered as Legacy code. 
	  There is nothing about Vector which List collection cannot do. Therefore Vector should be avoided.
	
	- default initial capacity is 10.
	- It doubles the default capacity.
	
	- It maintains insertion order.
	- It allows duplicate and null values.
	- Is is not fail-fast (ConcurrentModificationException).
	
HashSet (Set) : 

	- It doesnot allow duplicate. If you try to add a duplicate element, the old value would be overwritten.
	- It doesnot maintain any order.
	- It allows null values, however if you insert more than one nulls it would still return only one null value.
	
TreeSet (NavigableSet -> SortedSet -> Set) : 

	- TreeSet is similar to HashSet except that it sorts the elements in the ascending order.
	- It doesnot allow duplicate. If you try to add a duplicate element, the old value would be overwritten.
	- It doesnot allows null value.
	
LinkedHashSet (Set) : 

	- LinkedHashSet is similar to HashSet.
	- It maintains the insertion order.
	- It doesnot allow duplicate. If you try to add a duplicate element, the old value would be overwritten.
	- It allows null values, however if you insert more than one nulls it would still return only one null value.
	
HashMap (Map) :	

	- Used for storing Key & value pairs.
	- It doesnot maintain any order.
	- It allows null keys and null values.
	
TreeMap (NavigableMap -> SortedMap -> Map) : 

	- Used for storing Key & value pairs.
	- TreeMap is Red-Black tree based NavigableMap implementation. It is sorted according to the natural ordering of its keys.
	- It doesnot allow a null key.

LinkedHashMap (Map) : 

	- Used for storing Key & value pairs.
	- It maintain insertion order.
	- It allows null keys and null values.		
	
HashTable (Map), (Threadsafe) : 

	- The initial default capacity of Hashtable class is 11 whereas loadFactor is 0.75.
	- Hashtable uses single lock for whole data.	
	
	- Used for storing Key & value pairs.
	- It doesnot maintain any order.
	- It doesnot allows null key or null value.	
	- Is is not fail-fast (ConcurrentModificationException).	
	  
ConcurrentHashMap (ConcurrentMap -> Map) : 

	- It is the enhancement of HashMap. While dealing with Threads, HashMap is not a good choice because performance-wise HashMap is not up to the mark.
	- The underlined data structure for ConcurrentHashMap is Hashtable.
	- ConcurrentHashMap class is thread-safe.
	- In ConcurrentHashMap, the Object is divided into a number of segments according to the concurrency level. 
	  The default concurrency-level of ConcurrentHashMap is 16.
	- Creates a new, empty map with a default initial capacity (16), load factor (0.75) and concurrencyLevel (16)
	- In ConcurrentHashMap, at a time any number of threads can perform retrieval operation but for updated in the object, 
	  the thread must lock the particular segment in which the thread wants to operate. 
	  This type of locking mechanism is known as Segment locking or bucket locking. Hence at a time, 16 update operations can be performed by threads.  
	- Inserting null objects is not possible in ConcurrentHashMap as a key or value.  
	
	
Q&A : 

1. Iterator vs list-Iterator

	- Iterator is used for traversing List, Set, Map.
	  ListIterator is used for traversing List only, we cannot traverse Set using ListIterator.	
	- Iterator can traverse in only forward direction.
	  ListIterator can traverse a List in both the directions (forward and Backward).
	- We cannot obtain indexes while using Iterator.
	  We can obtain indexes at any point of time while traversing a list using ListIterator. The methods nextIndex() and previousIndex() are used for this purpose.
	- Iterator is fail fast (ConcurrentModificationException).
      ListIterator is not fail-fast.  
      
2. Iterator vs Iterable

	- An Iterable is a simple representation of a series of elements that can be iterated over. 
	  It does not have any iteration state such as a "current element". Instead, it has one method that produces an Iterator.
	
	- An Iterator is the object with iteration state. 
	  It lets you check if it has more elements using hasNext() and move to the next element (if any) using next().
      Typically, an Iterable should be able to produce any number of valid Iterators.
      
      
