# Java

Lamda : Assigning a function to a variable.

why lambda ?
 - it enables functional programming
 - readable and concise code (eliminate boiler-plate code)
 - enables support for parallel processing
 
The return type of lamda is interface with single abstract method (SAM).
Lamda replaces anonymous inner class.

Type Inference : 

		s -> s.length()
		- here we are not specifying s is of what type. The JVM is smart enough to take the type from interface. This is type inference.
 
Functional vs object oriented programming : 

  Java is a object oriented programming, we use functional way when needed. Functional programming makes code much readable and maintain.
  
this reference :

	In anonymous inner class, this is the reference of the inner class.
	In lambda, this is the reference of the outer class.
	
Streams : 

	- It is one of the feature of java 8.
	- It is not a collection. It doesn't store values. (It doesn't use memory)
	- It doesn't change the values. 
	  If you want the result, you can get it by using terminal operation (eg. Count()).
	  It is lazy evaluation.
	
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

1. Iterator vs list-Iterator : 

	- Iterator is used for traversing List, Set, Map.
	  ListIterator is used for traversing List only, we cannot traverse Set using ListIterator.	
	- Iterator can traverse in only forward direction.
	  ListIterator can traverse a List in both the directions (forward and Backward).
	- We cannot obtain indexes while using Iterator.
	  We can obtain indexes at any point of time while traversing a list using ListIterator. The methods nextIndex() and previousIndex() are used for this purpose.
	- Iterator is fail fast (ConcurrentModificationException).
      ListIterator is not fail-fast.  
      
2. Iterator vs Iterable : 

	- An Iterable is a simple representation of a series of elements that can be iterated over. 
	  It does not have any iteration state such as a "current element". Instead, it has one method that produces an Iterator.
	
	- An Iterator is the object with iteration state. 
	  It lets you check if it has more elements using hasNext() and move to the next element (if any) using next().
      Typically, an Iterable should be able to produce any number of valid Iterators.

3. Comparable vs Comparator
	            
   Comparable : 
   		
   		- provides single sorting sequence. We can sort on basis of single element. eg : name.
   		- affects original class ie. actual class is modified.      
   		- provides compareTo() method.
   		- java.lang package.
   		- We can sort the list of comparable type by Collections.sort(List).
   
   Comparator : 
   
   		- provides multiple sorting sequence. We can sort on basis of multiple elements. eg : name, id, price etc.
   		- doesn't affects original class ie. actual class is not modified.      
   		- provides compare() method.
   		- java.util package.
   		- We can sort the list of comparator type by Collections.sort(List, Comparator). 	
   		
4. GC
	
	Division of heap into Eden, Survivor and Tenured/Old spaces.

	Minor GC :
	
		- Collecting garbage from young space is called a minor GC.
		- Minor GC is always triggered when JVM is unable to allocate space for a new object. Eg, eden is getting full.
		- If most of the object in eden can be considered as garbage and are never copied to old space.
		
		- ParNew and DefNew are 2 young generation GC.
		- ParNew is multi-threaded GC used along with concurrent Mark Sweep.
		- DefNew is single-threaded GC used along with Serial Garbage Collector(stops application thread during both minor and major GC).
	
	Major GC : 
	
		- Major GC is cleaning the Tenured/Old space.
		
	Full GC : 	
	
		- Full GC is cleaning entire heap - both young and tenured spaces.	
		
5. Perm Gen :

		- PermGen is garbage collected like other parts of heap.
		- PermGen contains meta-data of the classes and the objects.
		- In java 8, it is replaced by metaspace.			   					

6. Map

	IdentityHashMap : 
	
		- It uses == instead of equals() for comparing keys.
		
	WeakHashMap :
	
		- It used weakreference. Key/value mapping is removed when the key is no longer referenced.
		
	EnumMap : 
	
		- Here keys are Enum constants.
		
7. why JAVA	is important ?

	- It eliminates the need for recompilation.
	- Write Once Run Anywhere (WORA).
	
8. Memory model 

	JVM (Java Virtual Machine) : 
	
	  - The abstract machine usually offers an environment that is based on run-time.
	  - In this environment, it is possible to write bytecodes.
	  - It is the one that calls main method in java code.
	  - When we compile .java file, java compiler generates the corresponding .class file. This .class file goes into various
	    steps when we run it. These steps together describes whole JVM.
	    
	JRE (Java Runtime Environment) : 
	
	  - With JRE, it is possible to execute the java bytecode, which is physically present in JVM.
	  
	JDK (Java Development Kit) : 
	
	  - This tool is essential for documenting, programming, compiling and setting the java programs.
	  
	Class Loader : 
		
		- Bootstrap class loader : It loads core java API classes present in the “JAVA_HOME/jre/lib” directory.
		  This path is popularly known as the bootstrap path.
		- Extension class loader : It loads the classes present in the extensions directories “JAVA_HOME/jre/lib/ext”(Extension path).
		  It is a child of the bootstrap class loader.
		- System/Application class loader: It is responsible to load classes from the application classpath. 
		  It internally uses Environment Variable which mapped to java.class.path.	
		  It is a child of the extension class loader.
										   
	JVM memory : 
	
		Method area : 
		
			- In the method area, all class level information like class name, immediate parent class name, methods and variables information etc. are stored, including static variables. 
			  There is only one method area per JVM, and it is a shared resource.
		      
		Heap area : 
		
			- Information of all objects is stored in the heap area. There is also one Heap Area per JVM. 
			  It is also a shared resource.
			  
		Stack area :  
		
			- For every thread, JVM creates one run-time stack which is stored here. 
			- Every block of this stack is called activation record/stack frame which stores methods calls. 
			- All local variables of that method are stored in their corresponding frame. 
			- After a thread terminates, its run-time stack will be destroyed by JVM. 
			- It is not a shared resource.	   
		
		PC Registers :  
		
			- Store address of current execution instruction of a thread. Obviously, each thread has separate PC Registers.
			
		Native method stacks : 
		
			- For every thread, a separate native stack is created. It stores native method information. 	
			
	 Interpreter : 
	 
	 	 - It interprets the bytecode line by line and then executes. 
	 	 - The disadvantage here is that when one method is called multiple times, every time interpretation is required.
	 	 
     JIT (just-in-time) : 

         - It is used to increase the efficiency of an interpreter. 
         - It compiles the entire bytecode and changes it to native code so whenever the interpreter sees repeated method calls, 
           JIT provides direct native code for that part so re-interpretation is not required, thus efficiency is improved.
           
     Garbage Collector : 
     
         - It destroys un-referenced objects.      					  									   					
	  
9. Java is not fully object-oriented : 

	There are 8 different type of primitive	such as byte, char, float, boolean, double, long, short, int are mainly used in java. 
	Since these are not objects, it is not fully object-oriented.
	
10. Constructor :

		- same name as class name.
		- it does not have return type.
		- it has 2 types. Default constructor and Parameterized constructor.
		
		- By making the constructor private, we can make the class singleton.
		
11. == vs equals() :

	== compares the reference of the object.
	equals() compares the value of the object.	
	
12. Continue vs Break

	Continue :
		
		- It can be used only in loop.
		- It doesn't terminate, it move on to the next iteration.
		
	Break : 
	
		- It can be used in both loop and switch statements.
		- It results in termination of loop or switch.
		
13. Static vs non-Static

	Static :
		
		- A static method is declared using static keyword.	
		- Static Methods can access static variables without any objects, 
		  however non-static methods and non-static variables can only be accessed using objects. 
		- Static method occupies less space and memory allocation happens once.  
		- A static method cannot be overridden being compile time binding.
		- this and super cannot be used in static context.
	
	Non-Static : 		
		
		- A non-static method can access both static as well as non-static members.
		- A non-static method may occupy more space. 
		  Memory allocation happens when method is invoked and memory is deallocated once method is executed completely.
		- A non-static method can be overridden being dynamic binding.
  
	Static class : 
	
		- A class can be made static only if it is a nested class.
		- Nested static class doesn’t need reference of Outer class.
		- A static class cannot access non-static members of the Outer class.
			
14. Why is the Java main method static?
	
	- It is because the object is not required to call a static method. 
	- If it were a non-static method, JVM creates an object first then call main() method that will lead the problem of extra memory allocation.
	
15. Can we execute a program without main() method?

		- No, one of the ways was the static block, but it was possible till JDK 1.6. 
		- Since JDK 1.7, it is not possible to execute a Java class without the main method.
		
16. Stack :

		- Stack Memory in Java is used for static memory allocation and the execution of a thread.
		- It contains primitive values that are specific to a method and references to objects that are in a heap.
		- Access to this memory is in Last-In-First-Out (LIFO) order.
		- It's automatically allocated and deallocated when method finishes execution.
		- If this memory is full, Java throws java.lang.StackOverFlowError.
		- Access to this memory is fast when compared to heap memory.
		- This memory is threadsafe as each thread operates in its own stack.
		
17. Heap : 

		- It's accessed via complex memory management techniques that include Young Generation, Old or Tenured Generation, and Permanent Generation.
		- If heap space is full, Java throws java.lang.OutOfMemoryError.
		- Access to this memory is relatively slower than stack memory.
		- It needs Garbage Collector to free up unused objects so as to keep the efficiency of the memory usage.
		- Unlike stack, a heap isn't threadsafe and needs to be guarded by properly synchronizing the code.						

18. Callable vs Runnable :		  
		
		Callable : 
			- Callable is introduced in JDK 5.0
			- Callable has call() method which returns value.
			- call method can throw checked exception.
		
		Runnable : 		
			- Runnable is introduced in JDK 1.0
			- Runnable has run() method which doesn't return any value.
			- run method can't throw checked exception.
OOPS : 
																
	- OOP is faster and easier to execute.
	- OOP provides a clear structure for the programs.
	- OOP helps to keep the Java code DRY "Don't Repeat Yourself", and makes the code easier to maintain, modify and debug.
	- OOP makes it possible to create full reusable applications with less code and shorter development time.
	
	
	Object : 
		
		- Object is a bundle of data and its behaviour(often known as methods).																
		- An Object can be defined as an instance of a class.
		- An object contains an address and takes up some space in memory.
		- Example: A dog is an object because it has states like color, name, breed, etc. as well as behaviors like wagging the tail, barking, eating, etc.
		
	Class : 
	
		- A class can be considered as a blueprint using which you can create as many objects as you like.
	
	Inheritance : 
	
		- The process by which one class acquires the properties(data members) and functionalities(methods) of another class is called inheritance.
		- The aim of inheritance is to provide the reusability of code.
		- Child class has IS-A relationship with the parent class.
		
		- Single Inheritance: refers to a child and parent class relationship where a child class extends parent class.
		- Multilevel inheritance: refers to a child and parent class relationship where a class extends the child class. 
		  For example class C extends class B and class B extends class A.
		- Hierarchical inheritance: refers to a child and parent class relationship where more than one classes extends the same class. 
		  For example, classes B, C & D extends the same class A.  
		- Hybrid inheritance: Combination of more than one types of inheritance in a single program. 
		  For example class A & B extends class C and another class D extends class A then this is a hybrid inheritance example because it is a combination of single and hierarchical inheritance.  
		  
	Polymorphism : 
	
		- Polymorphism in Java is a concept by which we can perform a single action in different ways. 
		- Polymorphism is derived from 2 Greek words: poly and morphs. The word "poly" means many and "morphs" means forms. 
		  So polymorphism means many forms.
		- There are two types of polymorphism in Java: compile-time polymorphism and runtime polymorphism.
		
		- A method is overridden, not the data members, so runtime polymorphism can't be achieved by data members.
		
	Abstraction : 
	
		- Abstraction is a process of hiding the implementation details and showing only functionality to the user.
		- Another way, it shows only essential things to the user and hides the internal details, 
		  for example, sending SMS where you type the text and send the message. 
		  You don't know the internal processing about the message delivery. 
		- There are two ways to achieve abstraction in java
			Abstract class (0 to 100%)
			Interface (100%)   
			
		- An abstract class must be declared with an abstract keyword.
		- It can have abstract and non-abstract methods.
		- It cannot be instantiated.
		- It can have constructors and static methods also.
		- It can have final methods which will force the subclass not to change the body of the method.	
		
	Encapsulation :
	
		- Binding (or wrapping) code and data together into a single unit are known as encapsulation. 
		  For example, a capsule, it is wrapped with different medicines	
		- However if we setup public getter and setter methods to update the private data fields then the outside class can access those private data fields via public methods.
		- This way data can only be accessed by public methods thus making the private fields and their implementation hidden for outside classes. 
		  That’s why encapsulation is known as data hiding.   
			
		  
SOLID : 

	Single Responsibility Principle : 
		
		- The single responsibility principle states that every Java class must perform a single functionality. 
		  Implementation of multiple functionalities in a single class mashup the code and if any modification 
		  is required may affect the whole class. 
		- It precise the code and the code can be easily maintained.		  
		
	Open-Closed Principle :
		
		- The open-closed principle states that according to new requirements the module should be open for extension but closed for modification.
		
	Liskov Substitution Principle : 
	
		- Derived types must be completely substitutable for their base types.
		- if class A is a subtype of class B, then we should be able to replace B with A without disrupting the behavior of our program.
		
	Interface Segregation : 
	
		- It simply means that larger interfaces should be split into smaller ones. 
		  By doing so, we can ensure that implementing classes only need to be concerned about the methods that are of interest to them.
		  
	Dependency Inversion : 
	
		- The principle of Dependency Inversion refers to the decoupling of software modules. 
		  This way, instead of high-level modules depending on low-level modules, both will depend on abstractions.
		  
	
ACID Properties (https://www.javatpoint.com/acid-properties-in-dbms) : 
	
	Atomicity : 
	
		- It means if any operation is performed on the data, either it should be performed or executed completely or should not be executed at all. 
		  It further means that the operation should not break in between or execute partially. 
		  In the case of executing operations on the transaction, the operation should be completely executed and not partially.
		  
	Consistency : 
	
		- The word consistency means that the value should remain preserved always. 
		  In DBMS, the integrity of the data should be maintained, which means if a change in the database is made, it should remain preserved always. 
		  In the case of transactions, the integrity of the data is very essential so that the database remains consistent before and after the transaction. 
		  The data should always be correct.
		  
	Isolation : 
		
		- The term 'isolation' means separation. 
		- It means if two operations are being performed on two different databases, they may not affect the value of one another. 
		- In the case of transactions, when two or more transactions occur simultaneously, the consistency should remain maintained. 
		- Any changes that occur in any particular transaction will not be seen by other transactions until the change is not committed in the memory.	  	  
			
	Durability : 
	
		- Durability ensures the permanency of something. 
		- In DBMS, the term durability ensures that the data after the successful execution of the operation becomes permanent in the database. 
		- The durability of the data should be so perfect that even if the system fails or leads to a crash, the database still survives.

		
Threads :

	Dirty Read :
	
		- method needs to be syncronised, so that it gets same value what has been set. Else it is dirty read.
		
	Read/Write lock :
	
		- Two threads reading the same resource does not cause problems for each other, so multiple threads that want to 
		  read the resource are granted access at the same time, overlapping. But, if a single thread wants to write to 
		  the resource, no other reads nor writes must be in progress at the same time. 
		  To solve this problem of allowing multiple readers but only one writer, you will need a read / write lock.
		  
		- It is worth noting that both unlockRead() and unlockWrite() calls notifyAll() rather than notify().
		- Inside the ReadWriteLock there are threads waiting for read access, and threads waiting for write access. 
		  If a thread awakened by notify() was a read access thread, it would be put back to waiting because there are 
		  threads waiting for write access. However, none of the threads awaiting write access are awakened, so nothing 
		  more happens. No threads gain neither read nor write access. By calling noftifyAll() all waiting threads are awakened 
		  and check if they can get the desired access. 
		  
	Reentrant lock (replacement of synchronous) :
	
		- ReentrantLock allows threads to enter into the lock on a resource more than once. When the thread first enters into the lock, 
		  a hold count is set to one. Before unlocking the thread can re-enter into lock again and every time hold count is incremented by one. 
		  For every unlocks request, hold count is decremented by one and when hold count is 0, the resource is unlocked. 	   
		  
	ThreadLocal : 
	
		- The Java ThreadLocal class enables you to create variables that can only be read and written by the same thread. 
		  Thus, even if two threads are executing the same code, and the code has a reference to the same ThreadLocal variable, 
		  the two threads cannot see each other's ThreadLocal variables.	  
		
ForkJoinPool :

	- Fork-join allows you to easily execute divide and conquer jobs, which have to be implemented manually if you want to execute it in ExecutorService. 
	  In practice ExecutorService is usually used to process many independent requests (aka transaction) concurrently, and fork-join when you want to 
	  accelerate one coherent job.		
	  
	- The ForkJoinPool makes it easy for tasks to split their work up into smaller tasks which are then submitted to the ForkJoinPool too. 
	  Tasks can keep splitting their work into smaller subtasks for as long as it makes to split up the task.  
	  
	  Fork : 

	  	- A task that uses the fork and join principle can fork (split) itself into smaller subtasks which can be executed concurrently.
	    - By splitting itself up into subtasks, each subtask can be executed in parallel by different CPUs, or different threads on the same CPU.
	    - The limit for when it makes sense to fork a task into subtasks is also called a threshold. 
	      It is up to each task to decide on a sensible threshold.	
	      
	  Join : 
	  
	  	- When a task has split itself up into subtasks, the task waits until the subtasks have finished executing.    
	  	- Once the subtasks have finished executing, the task may join (merge) all the results into one result.
	  	
	  - You create a ForkJoinPool using its constructor. As a parameter to the ForkJoinPool constructor you pass the indicated 
	    level of parallelism you desire. 	
	    
	    ForkJoinPool forkJoinPool = new ForkJoinPool(4);
	    
	    
	  	
		
https://www.callicoder.com/java-8-completablefuture-tutorial/#:~:text=CompletableFuture%20is%20used%20for%20asynchronous,its%20progress%2C%20completion%20or%20failure.
CompletableFuture (This class implements Future<T>, CompletionStage<T> interfaces) : 				
		
	- CompletableFuture is used for asynchronous programming in Java. 
	- Asynchronous programming is a means of writing non-blocking code by running a task on a separate thread 
	  than the main application thread and notifying the main thread about its progress, completion or failure.
	  
	What can be achieved in CompletableFuture over Future ?
		
		- Let’s say that you’ve written a function to fetch the latest price of an e-commerce product from a remote API. 
		  Since this API call is time-consuming, you’re running it in a separate thread and returning a Future from your function.
		  Now, let’s say that If the remote API service is down, then you want to complete the Future manually by the last cached price of the product.  						
		  
		- Future does not notify you of its completion. It provides a get() method which blocks until the result is available.
		  You don’t have the ability to attach a callback function to the Future and have it get called automatically when the Future’s result is available.
		  
		   - You can attach a callback to the CompletableFuture using thenApply(), thenAccept() and thenRun() methods  
		  
		- Sometimes you need to execute a long-running computation and when the computation is done, you need to send its result to 
		  another long-running computation, and so on. You can not create such asynchronous workflow with Futures.
		  
		   - CompletableFuture.supplyAsync(() -> {
				    return "Some Result"
				}).thenApplyAsync(result -> {
				    // Executed in a different thread from ForkJoinPool.commonPool()
				    return "Processed Result"
				})
		  
		- Let’s say that you have 10 different Futures that you want to run in parallel and then run some function 
		  after all of them completes. You can’t do this as well with Future.  
		  
		  	- the Supplier function passed to thenApply() callback would return a simple value but in this case, it is returning a CompletableFuture. 
		  	  Therefore, the final result in the above case is a nested CompletableFuture.

			- If you want the final result to be a top-level Future, use thenCompose() method instead.
			  CompletableFuture<Double> result = getUserDetail(userId)
					.thenCompose(user -> getCreditRating(user));
		  
		- Future API does not have any exception handling construct.
		
			- Handle exceptions using exceptionally() callback.
			- Handle exceptions using the generic handle() method.
		
	Methods : 
	
		CompletableFuture.runAsync : 
		
			- If you want to run some background task asynchronously and don’t want to return anything from the task, then you can 
			  use CompletableFuture.runAsync() method. It takes a Runnable object and returns CompletableFuture<Void>.
			  
		CompletableFuture.supplyAsync : 
		
			- It takes a Supplier<T> and returns CompletableFuture<T> where T is the type of the value obtained by calling the given supplier.
			
	A note about Executor and Thread Pool :
	
		- You might be wondering that - Well, I know that the runAsync() and supplyAsync() methods execute their tasks in a separate thread. 
		  But, we never created a thread right?
          Yes! CompletableFuture executes these tasks in a thread obtained from the global ForkJoinPool.commonPool().

		- But hey, you can also create a Thread Pool and pass it to runAsync() and supplyAsync() methods to let them execute 
		  their tasks in a thread obtained from your thread pool.

		- All the methods in the CompletableFuture API has two variants - One which accepts an Executor as an argument and one which doesn’t -

		Variations of runAsync() and supplyAsync() methods : 
			- static CompletableFuture<Void>  runAsync(Runnable runnable)
			- static CompletableFuture<Void>  runAsync(Runnable runnable, Executor executor)
			- static <U> CompletableFuture<U> supplyAsync(Supplier<U> supplier)
			- static <U> CompletableFuture<U> supplyAsync(Supplier<U> supplier, Executor executor)
					  	
  
	  
Completable feature
Fork join pool		
Thread (dirty read, dirty write, thread local, redundant lock, read lock,)
producer/consumer problem
Executable service
