## Java


#### Core
* What is the difference between `JDK` and `JRE`?

  <details>
  <summary>Answer</summary>
  
  When you download Java, you get the `Java Runtime Environment` (JRE). The `JRE` consists of the `Java Virtual Machine` (JVM), Java platform core classes, and supporting Java platform libraries. All three are required to run Java applications on your computer. 
  
  The `Java Development Kit` (JDK) is a collection of tools for developing Java applications. With the `JDK`, you can compile programs written in the Java Programming language and run them in a JVM. In addition, the `JDK` provides tools for packaging and distributing your applications.

  The `JDK` and the `JRE` share the Java Application Programming Interfaces (Java API). The Java API is a collection of prepackaged libraries developers use to create Java applications. The Java API makes development easier by providing the tools to complete many common programming tasks including string manipulation, date/time processing, networking, and implementing data structures (e.g., lists, maps, stacks, and queues).

  Source: https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html
  </details>
  
* What is `JVM`?
  <details>
  <summary>Answer</summary>
  
  The `Java Virtual Machine` (JVM) is an abstract computing machine. The `JVM` is a program that looks like a machine to the programs written to execute in it. This way, Java programs are written to the same set of interfaces and libraries. Each JVM implementation for a specific operating system, translates the Java programming instructions into instructions and commands that run on the local operating system. This way, Java programs achieve platform independence.
  
  The `JVM` knows nothing of the Java programming language, only of a particular binary format, the class file format. A class file contains `JVM` instructions (or bytecodes) and a symbol table, as well as other ancillary information.
  
  Source: https://www.oracle.com/webfolder/technetwork/tutorials/obe/java/gc01/index.html
  
  </details>
* What is object in Java? 
  <details>
  <summary>Answer</summary>
  
  **Object** - an entity that has *state*, *behavior* and *identity*.
  
  *State* is the data of an object.
  
  *Behavior* is functionality of an object (like methods, etc.).
  
  *Identity* is unique ID of an object, invisible for the user (smth generated inside JVM).
  </details>
  
* What is class?
  <details>
  <summary>Answer</summary>
  
  **Class** - smth like a template or blueprint from which objects are created. It's not a physical entity.
  
  In Java class can contain *fields*, *methods*, *constructors*, *blocks*, *nested class and interface*.
  </details>

* What is `Object` class in Java? What methods of this do you know?
  <details>
  <summary>Answer</summary>
  
  **Object** class is the root of the class hierarchy. Every class in Java has `Object` as a superclass. All objects implement the methods of this class.
  
  Methods:
  
  `clone()` - creates and returns a copy of this object
   
  `equals(Object obj)` - indicate an equality of objects
  
  `hashcode()` - returns a hash code value of this object
  
  `finalize()` - called by a GC when there are no more references to this object
  
  `notify()` - wakes up a single thread which is waiting on this object's monitor
  
  `notifyAll()` - wakes up all threads that are waiting on this object's monitor
  
  `wait()` - causes the current thread to wait until another thread invokes `notify()` or `notifyAll()` for this object
  
  `toString()` - returns a string representation of the object
 
  </details>
  
* What does `equals()` method do. What is the difference with `==` statement.
  <details>
  <summary>Answer</summary>
  
  `==` compares not objects but references.
  
  `equals()` **by default** works exactly like `==` under the hood. We must override it to make its work right. 
  
  `equals()` **must be** overriden if you want to compare object by their values (manually by `.equals()`, in comparable, in hashmap, etc.).
  </details>

* Why do you need `hashCode()`?
  <details>
  <summary>Answer</summary>
  
  To compare a lot of objects with only `equals()` can take too much time because we need to check every field (ideally) of every object (in the worst case). 
  
  `hashcode()` helps us to make the first quick check: 
  
  If hash codes are different there is no sense to make an `equals` check.
  </details>

* What is the relationship between `hashCode()` and `equals()`?
  <details>
  <summary>Answer</summary>
  
  1. Two **different** objects can have the same `hashCode`. So-called "collision".
  
  2. Two **equals** objects must have the same `hashCode`.
  
  We must avoid collisions as much as possible.
  
  Also, if we override `equals()` we **must** override `hashcode()`. 
  </details>

* What’s wrong if we override only `equals()` without `hashCode()`?
  <details>
  <summary>Answer</summary>
  
  There is a high probability that the comparing process will have wrong results (e.g. hash codes are different but objects are equals).
  
  </details>

#### Abstraction
* What is the abstraction?
  <details>
  <summary>Answer</summary>
  
  **Abstraction** is the process of hiding details and showing only essential information to the user.
  </details>
* What’s the difference between `abstract class` and `interface`?
  <details>
  <summary>Answer</summary>
  
  - `abstract class` can have **abstract and non-abstract** methods. `interface` can have **only abstract**.
  
  - `abstract class` can have **final/non-final, static/non-static** variables. `interface` can have **only final and static**.
  
  - `abstract class` can be extended, `interface` can be implemented.
  
  - `abstract class` can have variables with different modifiers, `interface` can have only **public** variables.
  </details>
* Can there be an `abstract method` without an `abstract class`?
  <details>
  <summary>Answer</summary>
  
  No.
  </details>
* Can the `Interface` be `final`? And `abstract class`?
  <details>
  <summary>Answer</summary>
  
  No. That's meaningless. Abstract constructions must be implemented to use.
  </details>
* What is a `marker interface`?
  <details>
  <summary>Answer</summary>
  
  **Marker interface** is an empty interface without any fields and methods. E.g. `Serializable`, `Cloneable`.
  </details>
* Can we define private and protected modifiers for the members in interfaces?
  <details>
  <summary>Answer</summary>
  
  No.
  </details>
  
#### Modifiers & keywords
* What access modifiers do you know?
  <details>
  <summary>Answer</summary>
  
  `private` - accessible only within the declared class.
  
  `default` - accessible only in the same package.
  
  `protected` - accessible in the same package and subclasses.
  
  `public` - accessible everywhere.
 
  </details>

* Which access modifier is more strict: protected or package-private?

  <details>
  <summary>Answer</summary>
  
  Package-private (`default`).
  </details>
* What does `final` keyword mean?

  <details>
  <summary>Answer</summary>
  
  `final` keyword means:
  
    - for classes: class can't be inherited by other classes
    - for methods: method can't be overriden
    - for variables: variable can't be modified
  </details>
* Does it make any sence to declare method `private final`?

  <details>
  <summary>Answer</summary>
  
  No. Because `private` methods are unavailable for overriding.
  </details>
* Can we declare the only constructor as `final`?

  <details>
  <summary>Answer</summary>
  
  Constructors are not inherited in Java. We can't override or modify it in another class even in subclass. 
  
  Hence we can't declare the only constructor as `final`. 
  </details>
  
* What does `static` keyword mean?

  <details>
  <summary>Answer</summary>
  
  The `static` keyword is used for a constant variable or a method that is the same for every instance of a class.
  
  Users can apply `static` keyword with variables, methods, blocks, and nested classes.
  
  When a member is declared `static`, it can be accessed before any objects of its class are created, and without reference to any object.
  </details>
  
* Can we declare the only constructor as `static`?

  <details>
  <summary>Answer</summary>
  
  No. Because the constructor is called when an object of a class is created. 
  </details>

#### Nested and Inner classes
* What is a `nested class`?
  <details>
  <summary>Answer</summary>

  `nested class` is a class inside another class. It's a member of its enclosing class.
  
  Non-static nested classes are called **inner classes**.
  
  Static nested classes are called **static nested classes**.
  
  Inner classes **have access** to other members of the enclosing class. Even if they are **private**.
  
  Static nested classes **don't have access** to other members of the enclosing class.
  
  Nested class can be `private`, `public`, `protected`, `package private`.
  
  Outer class can only be `public` or `package private`.
  
  </details>
* What are anonymous inner classes?
  <details>
  <summary>Answer</summary>
  
  **Anonymous inner classes** is an `inner class` without the name and with only single object created.
  
  It can be created from `interface` and `class` (abstract or default) aswell.
  </details>
* What is the `nested interface`?
  <details>
  <summary>Answer</summary>
  
  `nested interface` is an interface inside class or another interface. It can't be `private` there.
  
  </details>

#### Static Components

* What is `static` keyword we use for?

  <details>
  <summary>Answer</summary>
  
  The `static` keyword is mainly used for memory management in Java. Static component is the same for every instance of a class.
  </details>
* What components can be marked as `static`?
  <details>
  <summary>Answer</summary>
  
  - Blocks
  
  - Variables
  
  - Methods
  
  - Classes
  </details>
  
* Can we override `static` method?

  <details>
  <summary>Answer</summary>
  
  No, we can't. But we can create the same method in subclass.
  </details>
* What is `static class`? When should we use it? When shouldn't?

  <details>
  <summary>Answer</summary>
  
  Class can be made `static` only if it's a nested class. 
  
  Nested static classes were described [above](https://github.com/mzonov/Android-Interview-Questions#nested-and-inner-classes).
  </details>
* What are the restrictions that are applied to the Java `static` methods?

  <details>
  <summary>Answer</summary>
  
  - They can only call other static `methods` and use `static` variables.
  
  - They can't be overriden.
  
  - They can't refer to `this` or `super()`.
  </details>
* What is the `static` block?

  <details>
  <summary>Answer</summary>
  
  We use `static` block for initialization order if it's important for us.
  </details>
* Can we make constructors static?

  <details>
  <summary>Answer</summary>
  
  No.
  </details>
* Can we declare the static variables and methods in an `abstract class`?
  
  <details>
  <summary>Answer</summary>
  
  Yes.
  </details>

#### Strings
* What’s the difference between `new String("value")` and `"value"`?
  <details>
  <summary>Answer</summary>
  
  With `new` operator we create every time new object in the heap.
  
  If we use literal method it may return an existing object from the `String Pool`.
  </details>
* Is String mutable type or not? Why?
  <details>
  <summary>Answer</summary>
  
  Strings are **immutable**. Why:
  
  - Basically, the `String Pool` can work only with immutable strings.
  
  - Mutable strings would be a serious security problem. Hackers can't change the reference value, that's it.
  
  - Safety for multithreading. 
  </details>
* What is `String Pool`?
  <details>
  <summary>Answer</summary>
  
  It's a special memory space where strings (which are created via `= ""`) are stored by the JVM.
  </details>
* What is `String.intern()` method?
  <details>
  <summary>Answer</summary>
  
  We can store reference to string created with `new` operator to `String Pool` with `String.intern()`. Next time this string will be returned from String Pool.
  
  ```
  String constantString = "interned Baeldung";
  String newString = new String("interned Baeldung");

  assertThat(constantString).isNotSameAs(newString);

  String internedString = newString.intern();

  assertThat(constantString)
  .isSameAs(internedString);
  ```
  </details>
* What’s the difference between `String`, `StringBuilder` and `StringBuffer`.
  <details>
  <summary>Answer</summary>
  
  - The `+` operator uses `StringBuffer` to perform strings concatenation.
    
  - `StringBuffer` and `StringBuilder` are mutable. They provide `append()`, `insert()`, `delete()` methods for strings manipulation.
  
  - `StringBuffer` is synchronized but slow. `StringBuilder` is not synchronized but faster.
    
  </details>
* Why is it said that the `length()` method of String class doesn't return accurate results?
  <details>
  <summary>Answer</summary>
  
  Because `length()` can't recognize special symbols.
  </details>
* Why `CharArray()` is preferred over String to store the password?
  <details>
  <summary>Answer</summary>
  
  1. Strings are immutable. Another process can dump memory. So you can't modify strings to hide password until GC collect it.
  
  2. With array you can change items with what you want (e.g. blank items) after the work with password is done.
  </details>

#### Exceptions
* What exception types do you know? What are the differences?

  <details>
  <summary>Answer</summary>
  
  - **Checked** exceptions. These exceptions compiler can catch and show us all their places. We must handle them with `try-catch` block. 
  - **Unchecked** exceptions. The compiler doesn't expect these exceptions hence we can't handle them manually. We need to prevent these exceptions with code quality.
  </details>
* Describe an exception tree.
  <details>
  <summary>Answer</summary>
  
  - At the top of tree there is `Throwable` class.
  
  - `Throwable` is divided into `Exception` and `Error`. 
  
  - `Error` we can't handle manually. All `Error` classes are unchecked exceptions.
  
  - `Exception` are divided into checked and unchecked exceptions.
  </details>
* Name few classes at the top of exceptions ierarchy.
  <details>
  <summary>Answer</summary>
  
  `Throwable` class.
  </details>
* What is `Error`? Examples?

  <details>
  <summary>Answer</summary>
  
  `Error` is a critical JVM-error. In most cases we can't handle these exceptions. We have to only minimize errors with our code quality.
  </details>
* What construction we use for exception handling? Describe every part of it.

  <details>
  <summary>Answer</summary>
  
  `try-catch-finally`.
  
  In the `try` block we need to put code which could provoke `Exception`.

  In the `catch` block we need to put handling code when `Exception` has been caught.
  
  In the `finally` block we need to put code which must work in any case (has been `Exception` caught or not).
  
  </details>
* Can we use `try-finally` only (without `catch`)?

  <details>
  <summary>Answer</summary>
  
  Yes.
  </details>
* Imagine, we have `try-finally` block. In `try` block was thrown exception and execution was moved to `finally` block. In `finally` block an exception was thrown too. Which one exception would be ignored?

  <details>
  <summary>Answer</summary>
  
  An exception of `try` block would be ignored.
  </details>
* Does `finally` block always triggered? Is there any case when `finally` will not be executed?

  <details>
  <summary>Answer</summary>
  
  Yes, always. However it will not be triggered if we kill JVM with `System.exit()` in `try` or `catch` block.
  </details>
* Does exception catching order make any sence? E.g. which should be first: `IOException` or `FileNotFoundException`?

  <details>
  <summary>Answer</summary>
  
  Yes. The most concrete exception should take the first place in this column. The most abstract - the last place.
  </details>
* How we can create custom exception?

  <details>
  <summary>Answer</summary>
    
  We need to create `class` which extends `Exception`. Class name should be ended with `Exception` word to provide right compiler handling.
  
  Next, we need to create constructor with `super(message)` execution. It provides message showing like in plain `Exception`.
  </details>

#### Multithreading
* Differentiate between `process` and `thread`?
  <details>
  <summary>Answer</summary>
  
  `Process` has a self-contained execution environment. In particular, each process has its own memory space.
  
  Single application may in fact be a set of cooperatins processes. To provide communication between processes, most OS support `Inter Process Communication(IPC)` resources like pipes and sockets.
  
  Most implementations of the JAVM run as a single process. However every Java application can create additional processes.
  
  `Thread` are something like *lightweight processes*. Both processes and threads provide an execution environment, but creating a new thread requires fewer resources than creating a new process.

  Threads exist within a process: every process has at least one thread. Threads share the process's resources like memory and files.
  
  </details>
* What are `Thread` and `Runnable`?
  <details>
  <summary>Answer</summary>
  
  `Thread` object used for directly control thread creation and management.
  
  `Runnable` interface defines a single method `run`, meant to contain the code executed in the thread. The `Runnable` object is passed to the `Thread` constructor.
  </details>
* What’s the difference `Thread.stop()` and `Thread.interrupt()`?
  <details>
  <summary>Answer</summary>
  
  `Thread.stop()` is very old method. Since JDK8 it's gone.
  
  An **interrupt** is an indication to a thread that it should stop what it's dong. Interruptable thread must support its own interruption.
  
  `Thread` class has some methods which throws `InterruptedException` so we need to handle it with `try-catch` block.
  
  If any `Thread` method doesn't support `InterruptedException` so we need to check interruptions in `if (Thread.interrupted())` blocks.
  
  **The interrupt** mechanism is implemented using an internal flag so-called `interrupt status`. `Thread.interrupt()` sets this flag. `Thread.interrupted` clears this status. `Thread.isInterrupted` doesn't clear this status. So we need to use right method depending on the logic.
  </details>
* What does `join()` method?
  <details>
  <summary>Answer</summary>
  
  `join()` allows one thread to wait for the completion of another. It pauses current thread execution until another (on which we execute `join()` thread terminates.
  
  `join()` throws the `InterruptedException`.
  </details>
* Is it possible to start a thread twice?
  <details>
  <summary>Answer</summary>
  
  No. If we do so, an `IllegalThreadStateException` will be thrown.
  </details>
* What are the differences between `Mutex`, `Monitor` and `Semaphore`?
  <details>
  <summary>Answer</summary>
  
  `Mutex` (MUTual EXclusion) is a special object for threads synchronization. Every object has a mutex.
  
  `Mutex` has a mission of providing a mechanism so that only one thread has access to an object at a certain time. 
  
  We can't change `mutex` value manually. 
  
  `Monitor` is like a wrapping code around our code block/method which we want to synchronize.
  
  `Semaphore` is a mechanism for synchronization an access to some resource. This mechanism uses a counter. The counter tells us how many threads can simultaneously get the access to shared resource.
  
  We can manually set how many threads can simultaneously get the access.
  </details>
  
* What is `happens-before` relationship?
  <details>
  <summary>Answer</summary>
  
  That is relationship which simply guarantee that memory writes by one specific statement are visible to another specific statement.
  
  `happens-before` supports these rules:
  
  - releasing a monitor `happens-before` blocking this monitor
  
  - writing in `volatile` `happens-before` reading from `volatile`
  
  - writing value in `final` field during new object building `happens-before` writing this object in some variable
  </details>
* Why do we need `volatile`?
  <details>
  <summary>Answer</summary>
  
  Using `volatile` variables reduses the risk of memory consistency errors. Any write to bolatile variable establishes a `happens-before` relationship with subsequent reads of that same variable. 
  
  Changes to a `volatile` variable are always visible to other threads. 
  
  What's more, it also means that when a thread reads a `volatile` variable, it sees not just the latest change to the `volatile`, but also the side effects of the code that led up the change.
  </details>
* What does `sychronized` keyword do?
  <details>
  <summary>Answer</summary>
  
  - Making method `synchronized` prevents 2+ invocations of `synchronized` methods on the same object. When one thread is executing a synchronized method for an object, all other threads that invoke `synchronized methods` for the same object **suspend execution** until the first thread is done with the object.
  
  - `synchronized` method automatically establishes a `happens-before` relationship
  
  - We can create `synchronized` blocks with their own object as monitor to prevent extra blocking if it doesn't needed. E.g. code:
  
  ```
  public class MsLunch {
    private long c1 = 0;
    private long c2 = 0;
    private Object lock1 = new Object();
    private Object lock2 = new Object();

    public void inc1() {
        synchronized(lock1) {
            c1++;
        }
    }

    public void inc2() {
        synchronized(lock2) {
            c2++;
        }
    }
  }
  ```
  
  Class `MsLunch` has two instance fields, `c1` and `c2`, that are never used together. All updates of these fields must be synchronized, but there's no reason to prevent an update of `c1` from being interleaved with an update of `c2` — and doing so reduces concurrency by creating unnecessary blocking. Instead of using `synchronized` methods or otherwise using the lock associated with this, we create two objects solely to provide locks.
  </details>
  
* How does `synchronized` keyword work under the hood (briefly)?

  <details>
  <summary>Answer</summary>
  
  Synchronization is built around an internal entity **intrinsic lock** (or monitor).
  
  Every object has an intrinsic lock associated with it. By convention, a thread that needs exclusive and consistent access to an object's fields has to acquire the object's intrinsic lock before accessing them, and then release the intrinsic lock when it's done with them. A thread is said to own the intrinsic lock between the time it has acquired the lock and released the lock. As long as a thread owns an intrinsic lock, no other thread can acquire the same lock. The other thread will block when it attempts to acquire the lock.

  When a thread releases an intrinsic lock, a `happens-before` relationship is established between that action and any subsequent acquisition of the same lock.

  </details>
* What is used as `mutex` in `synchronized` method/block?
  <details>
  <summary>Answer</summary>
  
  By default the monitor is the object synchronized method/block is located. But we can always change it like this `synchronized(lock1)`. 
  </details>
* What is atomic operation? What's the difference with plain operation?
  <details>
  <summary>Answer</summary>
  
  The most of plain operations are not executing in one step. E.g. increment operation has these steps:
  
  1. Retrieve the current value of variable.
  
  2. Increment the retrieved value by 1.
  
  3. Store the incremented value back in variable.
  
  So if we use one variable in multithreading environment, we'll have a lot of mistakes.
  
  **Atomic operation acts in one step**. This operation can't stop in the middle.
  
  - Reads and writes are atomic for reference variables and for most primitive variables (all types except `long` and `double`).
  
  - Reads and writes are atomic for all variables declared `volatile` (including `long` and `double` variables).
  </details>
* Which classes in Java can handle atomic operations?
  <details>
  <summary>Answer</summary>
  Classes in `java.util.concurrent.atomic` package support atomic operations on single variables
  
  All classes have `get` and `set` methods that work like reads and writes on `volatile` variables. That is, a `set` has a `happens-before` relationship with any subsequent get on the same variable. The atomic `compareAndSet` method also has these memory consistency features, as do the simple atomic arithmetic methods that apply to integer atomic variables.
  </details>
* What is deadlock? 
  <details>
  <summary>Answer</summary>
  
  **Deadlock** describes a situation where two or more threads are blocked forever, waiting for each other.
  </details>
  
* What is starvation?
  <details>
  <summary>Answer</summary>
  
  **Starvation** describes a situation where a thread is unable to gain regular access to shared resources and is unable to make progress. This happens when shared resources are made unavailable for long periods by "greedy" threads. For example, suppose an object provides a synchronized method that often takes a long time to return. If one thread invokes this method frequently, other threads that also need frequent synchronized access to the same object will often be blocked.
  </details>
  
* What is livelock? 
  <details>
  <summary>Answer</summary>
  
  A thread often acts in response to the action of another thread. If the other thread's action is also a response to the action of another thread, then livelock may result. As with deadlock, livelocked threads are unable to make further progress. However, the threads are not blocked — they are simply too busy responding to each other to resume work. This is comparable to two people attempting to pass each other in a corridor: Alphonse moves to his left to let Gaston pass, while Gaston moves to his right to let Alphonse pass. Seeing that they are still blocking each other, Alphone moves to his right, while Gaston moves to his left. 
  </details>
* What is race condition? How to prevent?
  <details>
  <summary>Answer</summary>
  
  That is situation when two threads use shared resources and the order of code execution is unpredictable. So there may be a situation when one thread try to read already deleted information.
  </details>
  
* What are `Lock` objects in Java?
  <details>
  <summary>Answer</summary>
  
  Synchronized code relies on a simple kind of **reentrant lock**. This kind of lock is easy to use, but has many limitations. More sophisticated locking idioms are supported by the `java.util.concurrent.locks` package. 
  
  `Lock` objects work very much like the implicit locks used by synchronized code. As with implicit locks, only one thread can own a `Lock` object at a time. Lock objects also support a `wait/notify` mechanism.
  
  The biggest advantage of `Lock` objects over implicit locks is their ability to back out of an attempt to acquire a lock. The `tryLock` method backs out if the lock is not available immediately or before a timeout expires (if specified). The `lockInterruptibly` method backs out if another thread sends an interrupt before the lock is acquired.
  </details>
* What is double check lock? Usage example?
  <details>
  <summary>Answer</summary>
  
  </details>
* Which thread does GC use for garbage collection?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is the `Object.wait()` method? 
  <details>
  <summary>Answer</summary>
  
  Releases monitor and puts the calling thread into a wait state until another thread call the method `notify()` 
  </details>
* Why must `wait()`, `notify()` and `notifyAll()` methods be called from the synchronized block?
  <details>
  <summary>Answer</summary>
  
  Because `wait()`, `notify()` and `notifyAll()` methods are need monitor. So `synchronize` creates this monitor.
  </details>
* Imagine that in run-method was thrown `RuntimeException` which hadn’t been catched. What would happen with thread? Is it any way to know about this Exception? Could we resume thread work?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is `BlockingQueue`?
  <details>
  <summary>Answer</summary>
  
  A `Queue` that additionally supports operations that wait for the queue to become non-empty when retrieving an element, and wait for space to become available in the queue when storing an element.

  </details>
* What is the difference between Java `Callable` interface and `Runnable` interface?
  <details>
  <summary>Answer</summary>
  
  `Runnable` instances can be run by `Thread` class as well as `ExecutorService` but `Callable` instances can only be executed via `ExecutorService`.
  </details>

#### Network
* Give a brief description of Java socket programming?
* What is `Socket`?
* What is `Protobuf`?
* What is `WebSocket`?
* What is `WebRTC`? 

#### Other
* What is `JIT-compiler`?
* What is `ClassLoader`?
* What is `Java Reflection`? When should we use it?
* What is a native method?
* What is an `applet`?


## Java Memory Model

* What are the differences between `Heap` and `Stack`?

  <details>
  <summary>Answer</summary>
  
  The `stack` is used to store an order of methods execution and local variables.

  The stack memory is a physical space (in RAM) allocated to each thread at run time. It is created when a thread creates. Memory management in the stack follows `LIFO` order because it is accessible globally. It stores the variables, references to objects, and partial results. Memory allocated to stack lives until the function returns. If there is no space for creating the new objects, it throws the `java.lang.StackOverFlowError`. The scope of the elements is limited to their threads. The JVM creates a separate stack for each thread.

  The `heap` is used to store objects. It uses dynamic memory allocation/deallocation.
  
  It is created when the JVM starts up and used by the application as long as the application runs. It stores objects and JRE classes. Whenever we create objects it occupies space in the heap memory while the reference of that object creates in the stack. It does not follow any order like the `stack`. It dynamically handles the memory blocks. It means, we need not to handle the memory manually. For managing the memory automatically, Java provides the garbage collector that deletes the objects which are no longer being used. Memory allocated to heap lives until any one event, either program terminated or memory free does not occur. The elements are globally accessible in the application. It is a common memory space shared with all the threads. If the heap space is full, it throws the `java.lang.OutOfMemoryError`.
  
  The `heap` memory is further divided into the following memory areas:
  
  - Young generation
  - Survivor space
  - Old generation
  - Permanent generation
  - Code Cache
  
  Source: https://www.javatpoint.com/stack-vs-heap-java
  </details>

* What is a `Memory Leak`?

  <details>
  <summary>Answer</summary>
  
  Basically, the `Memory leak` occurs when programmers create a memory in `heap` and forget to delete it. 
  
  The consequences of the `memory leak` is that it reduces the performance of the computer by reducing the amount of available memory. Eventually, in the worst case, too much of the available memory may become allocated and all or part of the system or device stops working correctly, the application fails, or the system slows down.
  
  Source: https://www.geeksforgeeks.org/what-is-memory-leak-how-can-we-avoid/
  </details>
* How do you identify a `Memory Leak` in Android a?

  <details>
  <summary>Answer</summary>
  - Using [Memory Profiler](https://developer.android.com/studio/profile/memory-profiler) in Android Studio
  
  - Using [Leak Canary](https://square.github.io/leakcanary/) app
  
  </details>
* What is the `Garbage Collection`?
  <details>
  <summary>Answer</summary>
  
  `Automatic garbage collection` is the process of looking at heap memory, identifying which objects are in use and which are not, and deleting the unused objects. An in use object, or a referenced object, means that some part of your program still maintains a pointer to that object. An unused object, or unreferenced object, is no longer referenced by any part of your program. So the memory used by an unreferenced object can be reclaimed.

  </details>
* How is garbage collection controlled?

  <details>
  <summary>Answer</summary>
  
  In a programming language like C, allocating and deallocating memory is a manual process. In Java, process of deallocating memory is handled automatically by the garbage collector. The basic process can be described as follows.
  
  
  </details>
* Describe briefly how GC works.

  <details>
  <summary>Answer</summary>
  
  **Step 1: Marking**
  
  This is where the garbage collector identifies which pieces of memory are in use and which are not.
  
  **Step 2: Normal deletion**
  
  Normal deletion removes unreferenced objects leaving referenced objects and pointers to free space.

  The memory allocator holds references to blocks of free space where new object can be allocated.

  **Step 2a: Deletion with compacting**
  
  To further improve performance, in addition to deleting unreferenced objects, you can also compact the remaining referenced objects. By moving referenced object together, this makes new memory allocation much easier and faster.

  </details>
* How can an object be unreferenced?

  <details>
  <summary>Answer</summary>
  
  
  </details>
* What is the purpose of the `finalize()` method?

  <details>
  <summary>Answer</summary>
  
  
  </details>
* What reference types do you know? What are the differences between them?

  <details>
  <summary>Answer</summary>
  
  
  </details>


## Kotlin

#### General
* Tell me 5 features of Kotlin.
* What’s the difference between `val` and `var` keyword?
* Describe Kotlin access modifiers? Which one is default?
* How can we create constant?
* What are the differsences between sequence and collections approaches? 
* What’s the difference between nested and inner classes?
* What’s the difference between Kotlin `Any` and Java `Object`?
* What are `?` and `!!` signs?
* What’s the problem with usage of Java classes in Kotlin?
* Are Kotlin exceptions different from Java exceptions?
* What is `Nothing` type?
* What is `delegate`?
* What are `inline`/`crossinline`/`noinline` keywords? Maybe we should inline keyword everywhere?
* What is `reified` keyword? How does it work?
* What is `SAM`-interface?
* What’s the difference between `postValue()` and `setValue()` in `mutableLiveData`? 
* What is `backing field`?
* What is `destructuring declarations`?
* What does annotation `@JvmOverloads` mean?
* What is `TypeArray`? How does it work?

#### Extensions
* What are extensions under the hood?
* What we can do with extensions?
* Which class fields (accessibility modifiers) have extensions access to?
* What if we'll create an extension with the same signature as class method has? Which method will be lauched?
* How can we execute an extension in Java?

#### Data Class
* What is `data class` under the hood? What are the differences with plain java class? 
* Can we inherit class from data class?
* Can data class implement interface?
* What’s the difference between property and field?
* Does `hashcode` method of data class count field or it count only properties?

#### Sealed Class/Interface
* What is `sealed class` under the hood? How is it different from `Enum`?
* When should we use `sealed class`?
* What's the difference between `sealed class` and `sealed interface`?

#### Objects
* What is `covariance` and `contravariance`? 
* What’s the difference between `==` and `===` comparing?
* What’s the difference between `is` and `as` operators?
* How can we create `anonymous class`?

#### Syntactic Sugar
* What is `smart cast`?
* What is `typealias` keyword?
* What are `infix` functions? 
* When should we make property `lazy`? 
* How can we create `singleton` in Kotlin?
* What can we do with `let`, `run`, `also`, `apply`, `with` methods?


## Collections

* What is type erasing?
* Describe briefly collections tree.
* What is `Comparator`?
* What’s the difference between plain array and list?
* What’s the difference between `ArrayList` and `LinkedList?`?
* Which operations process slowly in List and Array? Which quickly?
* What is `Map`? What children it has?
* How does `HashMap` work?
* What we can use as `hash`? 
* What is the default size of load factor in hashing based collection?
* What are `Generics`? What are their advantages?
* What is the main feature of `TreeMap` or `TreeSet`?
* What is the difference between `HashSet` and `HashMap`?
* What is the difference between `HashMap` and `Hashtable`?


## Android

#### Core
* What is `Application` class?
* What is `Context`?
* What’s the difference between application context and activity context?
* What are `Activity` and `Fragment`? What’s the difference between them? 
* How can we launch `activity` and `fragment`? 
* Describe lifecycle of activity and fragment (+ during screen rotation).
* What are tasks and backstack.
* How can we transfer data between activities?
* What’s the difference between `Serializable` and `Parcelable`?
* Which Activity’s lifecycle method triggers during Dialog creation?
* What is `TargetFragment`?
* What is retained fragment?
* What is `ViewPager`? Is it `View` or `ViewGroup`? 
* What are runtime permissions? 
* What is `Intent`? What types of `Intent` do you know?
* What if we'll try to start activity via Service?
* What is `IntentFilter`? 
* What is `PendingIntent` in Android?
* What are different `launchMode` types available in Android?
* How can `activity` and `fragment` interact?
* How can we transfer data between fragments?
* In which case the lifecycle methods call chain would be like this: `onCreate()` -> `onDestroy()`?
* What if we call `finish()` in `onCreate()` method of Activity?
* When fragment’s `setRetain()` method doesn’t work
* What’s the difference in `addToBackStack` between `replace()` and `add()` methods?
* Can app work in multiple processes?
* What is `Service`? What are different types of services?
* `Bound Service` vs `Unbounded service`.
* How to start a `Foreground Service`?
* What is Sticky Intent in Android?
* What is `ContentProvider`?
* Can Content Provider be started before Application?
* What is `JIT`-compiler? What are advantages and disadvantages?
* How does the main thread work?
* Can any Android component be launched before `Application` component?
* What are the differences between `commit`, `commitNow` and `commitAllowingStateLoss`?
* Can we put fragments into each other?
* What is `IPC`? 
* Explain the `AndroidManifest` file and why do you need this?
* What is `ANR`? How to prevent it?
* How to reduce your app size?
* What is `Wake Lock`?
* What is `AIDL`?
* What is a `BroadcastReceiver`?
* What is a `LocalBroadcastManager`?
* How does `ViewModel` work internally? 

#### Data saving
* How to persist data in an Android app? 
* What is `ORM`?
* How would you preserve Activity state during a screen rotation?
* Explain `Scoped Storage` in Android.
* How to encrypt data in Android?
* What is `commit()` and `apply()` in SharedPreferences?

#### Memory
* What is the `onTrimMemory()` method? 
* Why does the `OutOfMemory` happen?
* How we can find memory leaks in Android app?

#### Push Notifications
* How can we handle Push Notifications?
* What is Firebase `topic`?
* What is Push `channel`?
* What is Firebase `token`?

#### UI
* What’s the difference between `View` and `ViewGroup`? 
* When should we use `FrameLayout`, `LinearLayout` or `ConstraintLayout`?
* What ways can we implement `Splash Screen`?
* What are `resources`?
* Why should we put strings and dimens into resources files?
* What are weight and orientation in `LinearLayout`? What is affect without orientation?
* `ConstraintLayout`: what are `bias`, `barrier`, `chain`, `guideline`.
* How can we maintain different screen sizes?
* What’s the difference between `dp` vs `sp`?
* Why is it better to use vector images?
* What are `include` and `merge` tags in xml?
* What’s the difference between `DataBinding` и `ViewBinding`?
* What is `Window`? Can application has one or multiple Window?
* Tell me about main lifecycle methods of `View`.
* What parameter should we handle in `onMeasure()`?
* What need we do for touches and gestures overriding?
* Describe briefly how `RecyclerView` works.
* What two methods must we implement in `DiffUtil`? What do they mean?
* When should we use `CoordinatorLayout`?
* How do the Touch Control and Events work in Android?

#### Network
* What is `REST`?
* What is `OkHttp`?
* What is `Retrofit`?
* What is `SSL`?
* How can we check internet connection?
* What is interceptor in `OkHttp`? Give examples of it.
* How would you handle token refreshing?
* What Http-methods do you know?

#### Testing
* What is Unit-testing?
* What is instrumented testing?
* What is UI-testing?
* What is `UI-Automator`?
* What testing libraries do you know?

#### Tools
* What is `ADB`?
* What is `Strict mode`?
* What is `Android Lint`?
* What is `Multidex` in Android?
* What does `Android Studio Profiler` help us to check?


## Multithreading
* What are actual and deprecated ways of multithreading implementation in Android development?
* What is `WorkManager`?
* Does `WorkManager` have any restrictions?
* When to use an Android service and when to use a thread

#### RxJava
* Describe the reactive approach.
* What are `subscribeOn` and `observeOn`? Is their order in chain important?
* What is scheduler in `RxJava`?
* What’s the difference between `IO` and `Computation` scheduler?
* When should we use `IO` and `Computation` schedulers? Is there any clear separation?
* What `source types` do you know? 
* What’s the difference between `cold` and `hot` source? 
* What’s the difference between `Observable` and `Flowable`?
* What is `backpressure`?
* What is backpressure strategy? 
* What’s the difference between `debounce` and `distinctUntilChanged`?
* What’s the difference between `map` and `flatmap`?
* How can we implement searching with these requirements: a) limit network requests with 500ms of idle; b) prevent network requests of similar strings.
* What is `Subject`? What types of this do you know?
* What ways of error handling do you know?
* Does `zip` operator acts in parallel or sequentially?

#### Coroutines
* What is `Coroutine`?
* What is `Coroutine Context`?
* What is `Job`?
* What is `Scope`?
* How we can cancel coroutine?
* How we can change dispatcher inside coroutine?
* What is `Dispatcher`?
* What is `Channel`?
* What is `Flow`?


## Dagger
* What is `dependencies graph`?
* What are Dagger `component`, `module` and `subcomponent`?
* What are the differences between `@Binds` and `@Provides`?
* How we can create the `component`?
* How to `inject` values at runtime in Dagger?
* What is `scope` in Dagger?
* How we can create our own `scope`?
* How to implement Dagger in multi module architecture?


## Architecture

* What are the differences between `MVVM`, `MVP`, `MVI` approaches?.
* What is `Moxy`? What is the main feature of this?
* Describe `SOLID` principles.
* What is `god object` and what examples in Android SDK do you know?
* What are the differences between `dependency injection`, `dependency inversion` and `control inversion`?
* Describe `Clean Architecture` and decompose it on layers.
* Describe `Single Activity` principle.
* What is `multi module` architecture? What are advantages of this?
* Describe 3 main principles of `OOP`.
* What’s the difference between `inheritance` and `composition`?
* What's the difference between `abstract factory` and `factory pattern`?
