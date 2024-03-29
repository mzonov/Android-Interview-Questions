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
* What is `JIT`-compiler? What are advantages and disadvantages?
  <details>
  <summary>Answer</summary>
  
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
  
  2. Two **identical** objects must have the same `hashCode`.
  
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
* What is `SAM`-interface?
  <details>
  <summary>Answer</summary>
  
  `Single Abstract Method` interface is an interface having only one abstract method.
  
  It means that it's easy to use with lambda.
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
* Does it make any sence to declare method as `private final`?

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
  
  **Anonymous inner class** is an `inner class` without the name and with only single object created.
  
  It can be created from `interface` and `class` (abstract or default) aswell.
  </details>
* What is the `nested interface`?
  <details>
  <summary>Answer</summary>
  
  `nested interface` is an interface inside class or another interface. It can't be `private` there.
  
  </details>

#### Static Components

* What does `static` keyword mean?

  <details>
  <summary>Answer</summary>
  
  The `static` keyword is used for a constant variable or a method that is the same for every instance of a class.
  
  Users can apply `static` keyword with variables, methods, blocks, and nested classes.
  
  When a member is declared `static`, it can be accessed before any objects of its class are created, and without reference to any object.
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

* Where are `static` components stored?
  <details>
  <summary>Answer</summary>
  
  Static components are stored in the `PermGen` section of the heap. 
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
* What exception types do you know? What's the difference between them?

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
* What's the difference between `Mutex`, `Monitor` and `Semaphore`?
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
* What's the difference between `synchronized` keyword and `ReadWriteLock`?
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
* What's the difference between atomic class and `volatile`?
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

* What's the difference between `Heap` and `Stack`?

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
* How do you identify a `Memory Leak` in Android?

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
  
  - By nulling the reference
  
  - By assigning a reference to another
  
  - By anonymous object etc.
  </details>
* What is the purpose of the `finalize()` method?

  <details>
  <summary>Answer</summary>
  
  The `finalize()` method is invoked each time before the object is garbage collected. This method can be used to perform cleanup processing.
  </details>
* What reference types do you know? What's the difference between them?

  <details>
  <summary>Answer</summary>
  
  1. **Strong reference**. This is the default type/class of Reference Object. Any object which has an active `strong reference` are not eligible for garbage collection. The object is garbage collected only when the variable which was strongly referenced points to null.
  
  2. **Weak reference**. If JVM detects an object with only `weak references` (i.e. no strong or soft references linked to any object object), this object will be marked for garbage collection.

  3. **Soft reference**. If an object has no strong reference but has a soft reference, then the garbage collector reclaims this object’s memory when GC needs to free up some memory.
  
  4. **Phantom reference**. `Phantom Reference` can be used in situations, where sometimes using finalize() is not  sensible.This is a special reference which says that the object was already finalized, and the garbage collector is ready to reclaim its memory.
  </details>


## Kotlin

#### General
* What’s the difference between `val` and `var` keyword?
  <details>
  <summary>Answer</summary>
  
  `val` variable is immutable, `var` is mutable.
  </details>
 
* Describe Kotlin access modifiers? Which one is default?
  <details>
  <summary>Answer</summary>
  
  - `private`
  - `protected`
  - `internal` - visible everywhere in the same module
  - `public` (default)
  </details>
* How can we create constant?
  <details>
  <summary>Answer</summary>
  
  - In `object` class
  - In `companion object` section of class
  - Outside of class
  </details>
  
* What's the difference between sequence and collections approaches? 
  <details>
  <summary>Answer</summary>
  
  **Collections** are eagerly evaluated — each operation is performed when it’s called and the result of the operation is stored in a new collection. The transformations on collections are `inline` functions.
  
  **Sequences** are lazily evaluated. They have two types of operations: intermediate and terminal. Intermediate operations are not performed on the spot; they’re just stored. Only when a terminal operation is called, the intermediate operations are triggered on each element in a row and finally, the terminal operation is applied. Intermediate operations (like map, distinct, groupBy etc) return another sequence whereas terminal operations (like first, toList, count etc) don’t.

  Sequences don’t hold a reference to the items of the collection. They’re created based on the iterator of the original collection and keep a reference to all the intermediate operations that need to be performed.

  Unlike transformations on collections, intermediate transformations on sequences are not inline functions — inline functions cannot be stored and sequences need to store them.
  
  Image illustrated principle difference between **collections** and **sequences**: https://typealias.com/img/guides/sequences-illustrated-guide/order-of-operations.png
  
  </details>
* What’s the difference between nested and inner classes?
  <details>
  <summary>Answer</summary>
  
  A nested class marked as `inner` can access the members of its outer class. Inner classes carry a reference to an object of an outer class.
  
  Nested class is like a static nested class in Java.
  </details>
* What’s the difference between Kotlin `Any` and Java `Object`?
  <details>
  <summary>Answer</summary>
  
  - `Any` is not `java.lang.Object`; in particular, it does not have any members other than `equals()`, `hashCode()` and `toString()`. But while compiling in Java other methods are appearing.
  
  - In Java, primitives types aren’t type of the hierarchy and you need to box them implicitly, while in Kotlin `Any` is a super type of all types.
  
  - `Any` can’t hold the `null` value, if you need `null` to be part of your variable you can use the type `Any?`
  </details>
* What are `?` and `!!` signs?
  <details>
  <summary>Answer</summary>
  
  `?` means that this variable or chain is nullable. 
  
  With `!!` we say compiler that this variable or chain not nullable.
  </details>
 
* What’s the problem with usage of Java classes in Kotlin?
  <details>
  <summary>Answer</summary>
  
  The type of java classes using in Kotlin is a platform type. It means that it has no `null` checking.
  </details>
* Are Kotlin exceptions different from Java exceptions?
  <details>
  <summary>Answer</summary>
  
  Yes. Kotlin exceptions are all unchecked.
  </details>
* What is `Nothing` type?
  <details>
  <summary>Answer</summary>
  
  `Nothing` type means that this function will never return anything. So the code after `Nothing` method is unreachable.
  
  This type is a subtype of all classes.
  
  Examples of usage:
  
  - `TODO` method
  
  - Method with throws an exception
  </details>
* What is `delegate`?
  <details>
  <summary>Answer</summary>
  
  It uses the **delegation pattern**. It is an object-oriented design pattern that allows object composition to achieve the same code reuse as inheritance.
  
  With some common kinds of properties, even though you can implement them manually every time you need them, it is more helpful to implement them once, add them to a library, and reuse them later.
  
  Property delegates don’t have to implement an interface, but they have to provide a `getValue()` function (and `setValue()` for `vars`).
  
  Standard famous delegates:
  
  - `lazy()`
  
  - `observable()`
  
  - `viewBinding()`
  </details>
* What is `inline` function? 
  <details>
  <summary>Answer</summary>
  
  Every time we declare a higher-order function, at least one instance of those special `Function*` types will be created (similar to `anonymous inner classes` in Java).
  
  In order to actually perform the operation encapsulated in a Kotlin lambda, the higher-order function will need to call the special method named `invoke` on the new instance. The result is more overhead due to the extra call.
  
  So, when we’re passing a lambda to a function, the following happens under the hood:

  - At least one instance of a special type is created and stored in the heap
  
  - An extra method call will always happen
  
  Also, Kotlin erases the `generic` type information at runtime. That is, an instance of a `generic` class doesn’t preserve its type parameters at runtime.
  
  **So, what does `inline` do?**
  
  When using `inline` functions, the compiler inlines the function body. That is, it substitutes the body directly into places where the function gets called. By default, the compiler inlines the code for both the function itself and the lambdas passed to it.
  
  **However**, we should not overuse the inline functions, especially for long functions since the inlining may cause the generated code to grow quite a bit.
  
  Source: https://www.baeldung.com/kotlin/inline-functions
  </details>
  
* What is the difference between `crossinline` and `noinline`?
  <details>
  <summary>Answer</summary>
  
  `noinline`:
  
  By default, all lambdas passed to an `inline` function would be inlined, too. However, we can mark some of the lambdas with the `noinline` keyword to exclude them from inlining.
  
  `crossinline`:
  It provides an opportunity of inlining lambda inside another lambda, not in current function. Example: 
  ```
  inline fun test4(crossinline f: () -> Unit) {
    thread { f() }
  }

  fun compiledMain4() {
      thread {
          println("start")
          println("stop")
      }
  }
  ```
  
  Source: https://www.baeldung.com/kotlin/crossinline-vs-noinline, 
  https://stackoverflow.com/a/51113423/7041761
  </details>
  
* Maybe we should to use the `inline` everywhere?
  <details>
  <summary>Answer</summary>
  
  The Kotlin team wants you to use the inlining feature sensibly. With inlining the size of the compiled code can explode dramatically and even hit the JVM limits of up to 64K bytecode instructions per method. The main use case is higher-order functions that avoid the cost of creating an actual lambda object, only to discard it right after a single function call which happens right away.

  Source: https://stackoverflow.com/a/51113423/7041761
  </details>
  
* What is `reified` keyword? How does it work?
  <details>
  <summary>Answer</summary>
  
  Kotlin erases the generic type information at runtime, but for `inline` functions, we can avoid this limitation. That is, the compiler can reify generic type information for inline functions.
  
  `inline fun <reified T> Any.isA(): Boolean = this is T`
  
  Without `inline` and `reified`, the `isA` function wouldn’t compile.

  Why `inline`? Because only in embedded code compiler can check the generic type.
  </details>
  
* What’s the difference between `postValue()` and `setValue()` in `mutableLiveData`? 
  <details>
  <summary>Answer</summary>
  
  `setValue()` must be used only from the main thread
  
  `postValue()` is asynchronous and can be used from any thread.
  </details>
  
* What is `property`?
  <details>
  <summary>Answer</summary>
  Properties in Kotlin classes can be declared either as mutable, using the `var` keyword, or as read-only, using the `val` keyword.
  
  The full syntax for declaring a property is as follows:

  ```
  var <propertyName>[: <PropertyType>] [= <property_initializer>]
    [<getter>]
    [<setter>]
  ```
  
  You can define custom accessors for a property. If you define a custom getter, it will be called every time you access the property (this way you can implement a computed property).
  
  If you need to annotate an accessor or change its visibility, but you don't need to change the default implementation, you can define the accessor without defining its body:

  ```
  var setterVisibility: String = "abc"
    private set // the setter is private and has the default implementation

  var setterWithAnnotation: Any? = null
    @Inject set // annotate the setter with Inject
  ```
  
  </details>
  
* What’s the difference between property and field?
  <details>
  <summary>Answer</summary>
  In Kotlin, a field is only used as a part of a property to hold its value in memory. Fields cannot be declared directly. However, when a property needs a backing field, Kotlin provides it automatically. 
  
  </details>

* What is `backing field`?
  <details>
  <summary>Answer</summary>
  
  This backing field can be referenced in the accessors using the field identifier:
  
  ```
  var counter = 0 // the initializer assigns the backing field directly
    set(value) {
        if (value >= 0)
            field = value
            // counter = value // ERROR StackOverflow: Using actual name 'counter' would make setter recursive
    }
  ```
  The field identifier can only be used in the accessors of the property.

  A backing field will be generated for a property if it uses the default implementation of at least one of the accessors, or if a custom accessor references it through the field identifier.
  </details>
  
* What is `destructuring declarations`?
  <details>
  <summary>Answer</summary>
  
  It creates multiple variables at once.
  
  ```
  val (name, age) = person
  ```
  
  It's compiled down to the following code:
  
  ```
  val name = person.component1()
  val age = person.component2()
  ```
  
  Examples of usage: 
  
  - returning two values from a function
  
  - in maps
  
  - We can use underscore instead of unused variables `val (_, status) = getResult()`
  
  - in lambdas
  
  Source: https://kotlinlang.org/docs/destructuring-declarations.html#example-returning-two-values-from-a-function
  </details>
* What does annotation `@JvmOverloads` mean?
  <details>
  <summary>Answer</summary>
  
  Kotlin supports predefined methods/constructors operators like `fun bar(a: Int=0, b: Double =0.0, c: String="default value")`.
  
  So we can execute this like `bar()`, `bar(1)`, `bar(1, 1.0), `bar("asd")`, etc.
  
  In Java we can't do this stuff. So the `@JvmOverloads` annotation means that Kotlin will overload all these options (like `bar()`, `bar(1)`, etc) for Java execution.
  </details>

#### Extensions
* What can we do with extensions?
  <details>
  <summary>Answer</summary>
    
  We can "extend" a desired class with custom function or property.
  </details>
    
* What are extensions under the hood?
  <details>
  <summary>Answer</summary>
    
  Under the hood, our extension function is actually a static function with the first parameter as the receiver object. It is enclosed in a class with name generated as the filename appended with `kt`.
    
  Example:
    
  ```
  fun String.second(): Char {
    if (isEmpty()) throw NoSuchElementException("Char sequence is empty.")
    if (length < 2) throw NoSuchElementException("Char sequence length is less than 2.")
    return this[1]
  }
  ```
  
  Converts to:
                   
  ```
  public final class ExtensionFunctionsKt {
   public static final char second(@NotNull String $receiver) {
      Intrinsics.checkParameterIsNotNull($receiver, "$receiver");
      CharSequence var1 = (CharSequence)$receiver;
      if (var1.length() == 0) {
         throw (Throwable)(new NoSuchElementException("Char sequence is empty."));
      } else if ($receiver.length() < 2) {
         throw (Throwable)(new NoSuchElementException("Char sequence length is less than 2."));
      } else {
         return $receiver.charAt(1);
      }
   }
  }
  ```
    
  Source: https://medium.com/tompee/idiomatic-kotlin-extension-functions-67735491851f
  </details>
* Which class fields (accessibility modifiers) have extensions access to?
  <details>
  <summary>Answer</summary>
    
  Extensions utilize the same visibility modifiers as regular functions declared in the same scope would. For example:

  An extension declared at the top level of a file has access to the other private top-level declarations in the same file.

  If an extension is declared outside its receiver type, it cannot access the receiver's private or protected members.
    
  Source: https://kotlinlang.org/docs/extensions.html#note-on-visibility
  </details>
* What if we'll create an extension with the same signature as class method has? Which method would be launched?
  <details>
  <summary>Answer</summary>
    
  Class method would be launched.
    
  Source: https://kotlinlang.org/docs/extensions.html#extensions-are-resolved-statically
  </details>
* How can we execute an extension in Java?
  <details>
  <summary>Answer</summary>
    
  We can add `kt` postfix to an extension class name and execute this in Java.
    
  E.g. the extension is in `Utils.kt` class.
    
  In java: `UtilsKt.getExtenstion()`
  </details>

#### Data Class
* What is `data class` under the hood? What's the difference between `data class` and plain class? 
  <details>
  <summary>Answer</summary>
    
  Under the hood that is plain class with implemented `equals()`, `hashCode()`, `toString()`, constructor and fields with getters/setters.
  
  </details>
    
* Why shouldn't we use `data class` everywhere?
  <details>
  <summary>Answer</summary>
  
  Because a lot of code would be generated. So build time and APK size would be increased.
  
  </details>
    
* Can we inherit class from data class?
  <details>
  <summary>Answer</summary>
  
  Yes
  
  </details>
* Can data class implement interface?
  <details>
  <summary>Answer</summary>
    
  Yes
  </details>
* How do `hashcode` and `equals` methods work in data class?
  <details>
  <summary>Answer</summary>
    
  - hashCode:

  Calculate hashCode for each property declared as constructor parameter in current class

  Return `h1 × 31n−1 + h2 × 31n−2 + … + hn`

  - equals (let parameter be named that):

  Check if that is instance of our class (instanceof-check)

  For each property declared as constructor parameter in current class, check if this.prop1 equals to that.prop1 (by invoking equals method).

  Source: https://discuss.kotlinlang.org/t/how-does-kotlin-implement-equals-and-hashcode/940
  </details>

#### Sealed Class/Interface
* What is `sealed class` under the hood? How is it different from `Enum`?
    
  <details>
  <summary>Answer</summary>
    
  `sealed class` under the hood is just an `abstract class`. Its childs just inherit this `abstract class`.
    
  `enum class` is a group of related constants, `sealed class` is a group of related classes with a different state.
  </details>
    
* When should we use `sealed class`?
  <details>
  <summary>Answer</summary>
    
  If we have a constrained amount of options with different fillings.
  </details>
    
* What's the difference between `sealed class` and `sealed interface`?
    
  <details>
  <summary>Answer</summary>
    
  Interfaces can implement multiple other interfaces, and sealed classes are limited to a single parent class
  </details>

#### Objects
* What is `covariance` and `contravariance`? 
* What’s the difference between `==` and `===` comparing?
* What’s the difference between `is` and `as` operators?
* How can we create `anonymous class`?

#### Syntactic Sugar
* What is `smart cast`?
  <details>
  <summary>Answer</summary>
  
  Kotlin compiler checks inside `if`/`when` statements different conditions of params/variables.
  </details>
* What is `typealias` keyword?
  <details>
  <summary>Answer</summary>
  
  It provides making new type from another one. In most cases it's used for shortening long type name.
  </details>
  
* What are `infix` functions? 
  <details>
  <summary>Answer</summary>
    
  Functions marked with the `infix` keyword can also be called using the `infix` notation (omitting the dot and the parentheses for the call). `Infix` functions must meet the following requirements:

  - They must be member functions or extension functions.

  - They must have a single parameter.

  - The parameter must not accept variable number of arguments and must have no default value.
  </details>
* When should we make property `lazy`? 
  <details>
  <summary>Answer</summary>
  
  When we need to initialize property with the first getting.
  </details>
* How can we create `singleton` in Kotlin?
  <details>
  <summary>Answer</summary>
  
  - With created `object` class
  
  - With created `companion object` in class
    
  </details>
* What can we do with `let`, `run`, `also`, `apply`, `with` methods?
  <details>
  <summary>Answer</summary>
    
  All these inline functions are different by:
    
  - object reference
    
  - return value
    
  This [picture](https://miro.medium.com/max/1400/0*wZoYYxqh_7_B8JQ2.png) shows the difference.
    
  Source: https://blog.kotlin-academy.com/mastering-kotlin-scoped-and-higher-order-functions-23e2dd34d660
  </details>


## Collections

* What is type erasure?
  <details>
  <summary>Answer</summary>
  
  Generics types are erasuring at runtime. E.g. List<String> type become to List type. So we don't know what types exist in the list.

  </details>
* What's the reason for type erasure?
  <details>
  <summary>Answer</summary>

  Type erasure useful for resource management – with erasure help it needs to save less information, so less memory needed.
  </details>
* Describe briefly collections tree.
    
  <details>
  <summary>Answer</summary>

  ![image](https://github.com/mzonov/Android-Interview-Questions/assets/22050131/94ef708a-fa91-4a8c-8465-1b5018cd566e)

  Source: https://kotlinlang.org/docs/collections-overview.html#collection-types
  </details>
* What is `Comparator`?
    
  <details>
  <summary>Answer</summary>

  That is an interface which provides a comparison function for imposing a total ordering between instances of the type T.

  Source: https://kotlinlang.org/api/latest/jvm/stdlib/kotlin/-comparator/
  </details>
* What’s the difference between `ArrayList` and `LinkedList`?
  <details>
  <summary>Answer</summary>

  `ArrayList` built as the wrapper of plain array. So it works as an array with some improvements like autoresize, etc.
  
  `LinkedList` is a list of nodes. Every node has the link to previous and next item (except the first and the last).

  So these approaches have different performance of different methods.

  </details>
* Which operations process slowly in List and Array? Which quickly?
  <details>
  <summary>Answer</summary>

  - `ArrayList` has O(1) complexity of getting random element. Because array has direct references to every element in the list. While `LinkedList` has O(n) complexity because it has to traverse the list from the beginning to n-th element.
 
  - `LinkedList` is faster in inserting/removing of first elements because it has just to change the links. While `ArrayList` has to shift all array to left (if removing) or right (if inserting). That's why we can't say that inserting/removing of random element is faster in `LinkedList` or `ArrayList` because both constructions have their own difficulties: `LinkedList` firstly gotta find the element (and it's costly if the element far from the beginning) and `ArrayList` in the end gotta shift whole remained array and reallocate memory for it.

  </details>
* What is `Map`? What children it has?
  <details>
  <summary>Answer</summary>

  It's not an inheritor of the `Collection` interface. It stores key-value pairs (or entries). Keys are unique but different keys can be paired with equal values.

  Source: https://kotlinlang.org/docs/collections-overview.html#map
  </details>
* How does `HashMap` work?
  <details>
  <summary>Answer</summary>

  So, you have **key** and **value**. Every **key** gotta be an unique object. Values could be either different and the same – it doesn't matter. The moment you're adding the key-value pair, `hashCode` under the hood is counting (or you can override it and count as you want). `hashCode` is the number counted by object's fields. In ideal world `hashcode` gotta be equal for every key. But how it works: let's say `hashMap` has the size of 16. So each `hashCode` gotta be converted to the number from 0 to 15 (the last element of the list of 16 elements). Converted `hashCode` may turn out to be the same as other object's `hashCode` – it's called "collision". 

  To resolve this collision stuff `HashMap` under the hood an array of buckets where each bucket is `LinkedList`. So if collision happened, algorythm compares keys with `compare()` function and if it find absolutely the same key it overwrites the element, otherwise it puts the element to the end of list.
  </details>
* What is the default size of load factor in hashing based collection?
  <details>
  <summary>Answer</summary>

  0.75. It means if the array is 3/4 full – it will be resized.
  </details>
* What are `Generics`? What are their advantages?
  <details>
  <summary>Answer</summary>

  
  </details>
* What is the main feature of `TreeMap` or `TreeSet`?
  <details>
  <summary>Answer</summary>

  All elements are sorted in ascending order by default.
  </details>
* What is the difference between `HashSet` and `HashMap`?
  <details>
  <summary>Answer</summary>

  `HashMap` implements `Map` interface. `HashSet` implements `Set` interface but works with `HashMap` algorythm, where the key is the object itself.
  </details>
* What is the difference between `HashMap` and `Hashtable`?
  <details>
  <summary>Answer</summary>

  - `HashMap` is a non-synchronized unordered key-value pair map. It allows empty values and uses the hash code as an equality check, while `Hashtable` is a synchronized ordered map of key-value pairs. It does not allow empty values and uses the `equals()` method to check for equality.

  - `HashMap` has default capacity of 16 while `Hashtable` – 11.

  - The values of a `HashMap` object are enumerated using an `iterator`, and `Hashtable` is the only class other than vector that uses an `enumerator` to enumerate the values of a `Hashtable` object.
 
  Source: https://medium.com/@sweetaps1995/difference-between-hashmap-hashtable-4a1c148bb5dd
  </details>


## Android

#### Core
* List all main components of Android. What do they have in common?
  <details>
  <summary>Answer</summary>
  
  - Activity
  
  - Service
  
  - BroadcastReceiver
    
  - ContentProvider
    
  All of them can be an application entry point.
  </details>
* What is `Application` class?
  <details>
  <summary>Answer</summary>
  
  The `Application` class in Android is the base class within an Android app that contains all other components such as activities and services. The Application class, or any subclass of the Application class, is instantiated before any other class when the process for your application/package is created.
    
  This class is primarily used for initialization of global state before the first `Activity` is displayed. 
    
  Source: https://guides.codepath.com/android/Understanding-the-Android-Application-Class
  </details>
* What are tasks and backstack.
  <details>
  <summary>Answer</summary>
  
  **A task** is a collection of activities that users interact with when trying to do something in your app. These activities are arranged in a stack — **the back stack** — in the order in which each activity is opened.
  
  Source: https://developer.android.com/guide/components/activities/tasks-and-back-stack
  </details>
* What are different `launchMode` types available in Android?
  <details>
  <summary>Answer</summary>
  
  The launchMode attribute specifies an instruction on how the activity should be launched into a task. There are five different launch modes you can assign to the launchMode attribute:
  
  - `standard` (default). The system creates a new instance of the activity in the task from which it was started. The activity can be instantiated multiple times, each instance can belong to different tasks, and one task can have multiple instances.

  - `singleTop`. If an instance of the activity already exists at the top of the current task, the system routes the intent to that instance through a call to its `onNewIntent()` method, rather than creating a new instance of the activity.
  
  - `singleTask`. The system creates the activity at the root of a new task or locates the activity on an existing task with the same affinity. If an instance of the activity already exists and is at the root of the task, the system routes the intent to existing instance through a call to its `onNewIntent()` method, rather than creating a new instance. Meanwhile all of the other activities on top of it are destroyed.

  - `singleInstance`. Same as `singleTask`, except that the system doesn't launch any other activities into the task holding the instance. The activity is always the single and only member of its task; any activities started by this one open in a separate task.
  
  - `singleInstancePerTask`. The activity can only be running as the root activity of the task, the first activity that created the task, and therefore there will only be one instance of this activity in a task. In contrast to the `singleTask` launch mode, this activity can be started in multiple instances in different tasks if the `FLAG_ACTIVITY_MULTIPLE_TASK` or `FLAG_ACTIVITY_NEW_DOCUMENT` flag is set.
  
  Source: https://developer.android.com/guide/components/activities/tasks-and-back-stack
  </details>
* What are different Intent flags of launch mode types are available in Android?
  <details>
  <summary>Answer</summary>
  
  - `FLAG_ACTIVITY_NEW_TASK`. The same behavior as the `singleTask` launchMode.
  
  - `FLAG_ACTIVITY_SINGLE_TOP`. The same behavior as the `singleTop` launchMode.
  
  - `FLAG_ACTIVITY_CLEAR_TOP`. If the activity being started is already running in the current task, then instead of launching a new instance of that activity, all of the other activities on top of it are destroyed and this intent is delivered to the resumed instance of the activity (now on top), through `onNewIntent()`).
  </details>
* What is `taskAffinity`?
  <details>
  <summary>Answer</summary>
  
  An affinity indicates which task an activity prefers to belong to. By default, all the activities from the same app have an affinity for each other. So, by default, all activities in the same app prefer to be in the same task.
  
  You can modify the affinity for any given activity with the `taskAffinity` attribute of the `<activity>` element.
  
  The `taskAffinity` attribute takes a string value, which must be unique from the default package name declared in the `<manifest>` element, because the system uses that name to identify the default task affinity for the app.
  
  The affinity comes into play in two circumstances:

  - When the intent that launches an activity contains the `FLAG_ACTIVITY_NEW_TASK` flag.
  
  A new activity is, by default, launched into the task of the activity that called `startActivity()`.

  It's pushed onto the same back stack as the caller. However, if the intent passed to `startActivity()` contains the `FLAG_ACTIVITY_NEW_TASK` flag, the system looks for a different task to house the new activity. Often, it's a new task. However, it doesn't have to be. If there's already an existing task with the same affinity as the new activity, the activity is launched into that task. If not, it begins a new task.
  
  - When an activity has its `allowTaskReparenting` attribute set to `true`.
  
  In this case, the activity can move from the task it starts to the task it has an affinity for, when that task comes to the foreground.

  For example, suppose that an activity that reports weather conditions in selected cities is defined as part of a travel app. It has the same affinity as other activities in the same app (the default app affinity) and it allows re-parenting with this attribute. When one of your activities starts the weather reporter activity, it initially belongs to the same task as your activity. However, when the travel app's task comes to the foreground, the weather reporter activity is reassigned to that task and displayed within it.
    
  Source: https://developer.android.com/guide/components/activities/tasks-and-back-stack#Affinities
  </details>
* What’s the difference between `Serializable` and `Parcelable`?
  <details>
  <summary>Answer</summary>
  
  </details>
* What are runtime permissions? 
  <details>
  <summary>Answer</summary>
  
  </details>
* In which case the lifecycle methods call chain would be like this: `onCreate()` -> `onDestroy()`?
  <details>
  <summary>Answer</summary>
  
  If we call `System.exit()` or `finish()` in `onCreate()`.
  </details>
* Can any component be started before `Application` class? If yes, which component?
  <details>
  <summary>Answer</summary>
  
  Yes. `Content Provider` is launching before the `Application` class.
  </details>
* How does the main thread work?
  <details>
  <summary>Answer</summary>
  
  </details>
* Explain the `AndroidManifest` file and why do you need this?
  <details>
  <summary>Answer</summary>
  
  The `manifest` file describes essential information about your app to the Android build tools, the Android operating system, and Google Play.
  
  The `manifest` file is required to declare the following:
  
  - The components of the app, which include all activities, services, broadcast receivers, and content providers.
  
  - The permissions that the app needs in order to access protected parts of the system or other apps. It also declares any permissions that other apps must have if they want to access content from this app.
  
  - The hardware and software features the app requires, which affects which devices can install the app from Google Play.
  
  Source: https://developer.android.com/guide/topics/manifest/manifest-intro
  </details>
* What is `ANR`? How to prevent it?
  <details>
  <summary>Answer</summary>
  
  </details>
* How to reduce your app size?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is `Wake Lock`?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is `AIDL`?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is `TypedArray`?
  <details>
  <summary>Answer</summary>
  
  </details>
* What is Doze Mode?
  <details>
  <summary>Answer</summary>
  
  TODO: read about JobScheduler
  </details>
* How to do smth in our app during Doze Mode?
  <details>
  <summary>Answer</summary>
  
  </details>
* How does `ViewModel` survives during screen orientation? 
  <details>
  <summary>Answer</summary>
  
  1. Fragment or Activity keep `ViewModel` in `ViewModelStore`. This class basically is a wrapper of HashMap<String, ViewModel>.
    
  2. If there is no `ViewModel` of our Activity/Fragment in `ViewModelStore`, new `ViewModel` will be created.
    
  3. How does the `ViewModelStore` survives during screen orientation? We're getting this class from `NonConfigurationInstances` which survives configuration changes.
    
  4. When activity is destroying it writes `ViewModelStore` in `NonConfigurationInstances` with `onRetainNonConfigurationInstance()` method.
    
    `onRetainNonConfigurationInstance()` in documentation:
    
    ```
    Called by the system, as part of destroying an activity due to a configuration change, when it is known that a new instance will immediately be created for the new configuration. You can return any object you like here, including the activity instance itself, which can later be retrieved by calling getLastNonConfigurationInstance() in the new activity instance.
    ```
    
  5. During the activity's recreation it gets old `ViewModelStore` from `NonConfigurationInstances` with `onRetainNonConfigurationInstance()` or creates new `ViewModelStore` if there is no old `ViewModelStore`.
    
  Source: https://arkadiuszchmura.com/posts/how-viewmodels-survive-configuration-changes/, 
  </details>
    
#### Context
* What is `Context`?
  <details>
  <summary>Answer</summary>
    
  Due to [Android documentation](https://developer.android.com/reference/android/content/Context) the `context` is:
  
  Interface to global information about an application environment. This is an abstract class whose implementation is provided by the Android system. It allows access to application-specific resources and classes, as well as up-calls for application-level operations such as launching activities, broadcasting and receiving intents, etc.
    
  We can break the context and its use into three major points: 

  - It allows us to access resources.
  
  - It allows us to interact with other Android components by sending messages.
  
  - It gives you information about your app environment.
    
  Source: https://www.geeksforgeeks.org/what-is-context-in-android/
  </details>
* What’s the difference between application context and activity context?
  <details>
  <summary>Answer</summary>
  
  **Application context**:
    
  This context is tied to the life cycle of an application.
    
  There are some use cases:
    
  - Load Resource Values
  
  - Start a Service
  
  - Bind to a Service
  
  - Send a Broadcast
  
  - Register BroadcastReceiver
    
  **Activity context**:
    
  It is tied to the life cycle of activity.
    
  There are some use cases:
    
  - Load Resource Values

  - Layout Inflation

  - Start an Activity

  - Show a Dialog

  - Start a Service

  - Bind to a Service

  - Send a Broadcast

  - Register BroadcastReceiver
    
  The difference is that Application’s Context is not UI related. It means that, we shouldn’t use it to Inflate a Layout, Start an Activity nor Show a Dialog. Regarding the rest of the functionalities from Activity’s Context, they are available from Application’s Context also.
    
  Source: https://www.geeksforgeeks.org/what-is-context-in-android/, https://medium.com/@banmarkovic/what-is-context-in-android-and-which-one-should-you-use-e1a8c6529652
  </details>
* What if we launch `activity` with `app context`?
  <details>
  <summary>Answer</summary>
  
  </details>
    
#### Activity
* What is `activity`?
  <details>
  <summary>Answer</summary>
  
  `activity` is the crucial component for UI creation in Android application.
  
  Unlike programming paradigms in which apps are launched with a `main()` method, the Android system initiates code in an `activity` instance by invoking specific callback methods that correspond to specific stages of its lifecycle.
  </details>
* How can we launch `activity`
  <details>
  <summary>Answer</summary>
  
  - We can use `intent` component for launching new activity.
  
  - If activity is the start point so we need to check it in `Manifest` as `android.intent.action.MAIN` `intent-filter`
  </details>
* Describe `activity` lifecycle. What does it happen during screen rotation?
  <details>
  <summary>Answer</summary>
  
  `onCreate()`
  
  You must implement this callback, which fires when the system creates your activity. Your implementation should initialize the essential components of your activity: For example, your app should create views and bind data to lists here. Most importantly, this is where you must call `setContentView()` to define the layout for the activity's user interface.
  
  `onStart()`
  
  The activity becomes visible to the user. This callback contains what amounts to the activity’s final preparations for coming to the foreground and becoming interactive.
  
  `onResume()`
  
  The system invokes this callback just before the activity starts interacting with the user. At this point, the activity is at the top of the activity stack, and captures all user input. Most of an app’s core functionality is implemented in the `onResume()` method.
  
  In multi-window mode, however, your activity may be fully visible even when it is in the Paused state. For example, when the user is in multi-window mode and taps the other window that does not contain your activity, your activity will move to the Paused state.
  
  `onPause()`
  
  The system calls `onPause()` when the activity loses focus and enters a Paused state. This state occurs when, for example, the user taps the Back or Recents button. When the system calls `onPause()` for your activity, it technically means your activity is still partially visible, but most often is an indication that the user is leaving the activity, and the activity will soon enter the Stopped or Resumed state.

  An activity in the Paused state may continue to update the UI if the user is expecting the UI to update. Examples of such an activity include one showing a navigation map screen or a media player playing. Even if such activities lose focus, the user expects their UI to continue updating.

  You should **not** use `onPause()` to save application or user data, make network calls, or execute database transactions.
  
  *Note:* The app stays in this state until something happens to take focus away from the app.

  `onStop()`
  
  The system calls `onStop()` when the activity is no longer visible to the user. This may happen because the activity is being destroyed, a new activity is starting, or an existing activity is entering a Resumed state and is covering the stopped activity. In all of these cases, the stopped activity is no longer visible at all.
  
  You should also use `onStop()` to perform relatively CPU-intensive shutdown operations. For example, if you can't find a more opportune time to save information to a database, you might do so during `onStop()`.
  
  *Note:* Once your activity is stopped, the system might destroy the process that contains the activity if the system needs to recover memory. Even if the system destroys the process while the activity is stopped, the system still retains the state of the `View` objects (such as text in an `EditText` widget) in a `Bundle` (a blob of key-value pairs) and restores them if the user navigates back to the activity.
  
  `onRestart()`
  
  The system invokes this callback when an activity in the Stopped state is about to restart. onRestart() restores the state of the activity from the time that it was stopped. 

  This callback is always followed by `onStart()`.
  
  `onDestroy()`
  
  This callback is the final one that the activity receives. `onDestroy()` is usually implemented to ensure that all of an activity’s resources are released when the activity, or the process containing it, is destroyed.
  
  Image of lifecycle: https://developer.android.com/guide/components/images/activity_lifecycle.png
  
  Source: https://developer.android.com/guide/components/activities/intro-activities#mtal
  </details>
* Which `activity` lifecycle method triggers during Dialog creation?
  <details>
  <summary>Answer</summary>
  
  `onPause()`. As long as the activity is still partially visible but not in focus, it remains paused.
  
  Source: https://developer.android.com/guide/components/activities/activity-lifecycle#onpause
  </details>
* What is `onSaveInstanceState()` method?
  <details>
  <summary>Answer</summary>
  
  As your activity begins to stop, the system calls the `onSaveInstanceState()` method so your activity can save state information to an instance state bundle. The default implementation of this method saves transient information about the state of the activity's view hierarchy, such as the text in an EditText widget or the scroll position of a `ListView` widget.

  To save additional instance state information for your activity, you must override `onSaveInstanceState()` and add key-value pairs to the `Bundle` object that is saved in the event that your activity is destroyed unexpectedly.
  
  When your activity is recreated after it was previously destroyed, you can recover your saved instance state from the Bundle that the system passes to your activity. Both the `onCreate()` and `onRestoreInstanceState()` callback methods receive the same `Bundle` that contains the instance state information.

  Because the `onCreate()` method is called whether the system is creating a new instance of your activity or recreating a previous one, you must check whether the state `Bundle` is null before you attempt to read it. If it is null, then the system is creating a new instance of the activity, instead of restoring a previous one that was destroyed.
  
  Source: https://developer.android.com/guide/components/activities/activity-lifecycle#save-simple,-lightweight-ui-state-using-onsaveinstancestate
  </details>
* Which methods are being called in multi-window mode?
  <details>
  <summary>Answer</summary>
  
  When the user switches from app A to app B, the system calls `onPause()` on app A, and `onResume()` on app B. It switches between these two methods each time the user toggles between apps.
  
  Source: https://developer.android.com/guide/components/activities/state-changes#multiwindow
  </details>
* Which methods are being called when user clicks on back button?
  <details>
  <summary>Answer</summary>
  
  If an activity is in the foreground, and the user presses or gestures Back, the activity transitions through the `onPause()`, `onStop()`, and `onDestroy()` callbacks. In addition to being destroyed, the activity is also removed from the back stack.
  
  Source: https://developer.android.com/guide/components/activities/state-changes#multiwindow
  </details>

* How can we transfer data between activities?
  <details>
  <summary>Answer</summary>
  
  Via `Bundle` into which we can put the data during the `intent` object creation.
  </details>
* What if we call `finish()` in `onCreate()` method of Activity?
  <details>
  <summary>Answer</summary>
  
  `onDestroy()` will be immediately called after `onCreate()` without any of the rest of the activity lifecycle (`onStart()`, `onResume()`, `onPause()`, etc) executing.
  
  Source: https://developer.android.com/reference/android/app/Activity#onCreate(android.os.Bundle)
  </details>
* Can we start `activity` from `service`?
  <details>
  <summary>Answer</summary>
  
  From Android 10 (API 29) we can't start activities directly from `service`.
  
  Source: https://developer.android.com/guide/components/activities/background-starts
  </details>
    
#### Fragment
* What is `fragment`?
  <details>
  <summary>Answer</summary>
  
  A `Fragment` represents a reusable portion of your app's UI. A `fragment` defines and manages its own layout, has its own lifecycle, and can handle its own input events. `Fragments` cannot live on their own - they must be hosted by an activity or another fragment. The `fragment`’s view hierarchy becomes part of, or attaches to, the host’s view hierarchy.
  
  Source: https://developer.android.com/guide/fragments
  </details>
* What is `DialogFragment`?
  <details>
  <summary>Answer</summary>
  
  A DialogFragment is a special fragment subclass that is designed for creating and hosting dialogs. Strictly speaking, you do not need to host your dialog within a fragment, but doing so allows the FragmentManager to manage the state of the dialog and automatically restore the dialog when a configuration change occurs.
  
  Source: https://developer.android.com/guide/fragments/dialogs
  </details>
* What is `FragmentContainerView`?
  <details>
  <summary>Answer</summary>
  
  It is strongly recommended to always use a `FragmentContainerView` as the container for fragments, as `FragmentContainerView` includes fixes specific to fragments that other view groups such as `FrameLayout` do not provide.
  
  Source: https://developer.android.com/guide/fragments/create
  </details>
* How can we launch `fragment`?
  <details>
  <summary>Answer</summary>
  
  To display a fragment within a layout container, use the `FragmentManager` to create a `FragmentTransaction`. Within the transaction, you can then perform an `add()` or `replace()` operation on the container.
  
  Source: https://developer.android.com/guide/fragments/fragmentmanager
  </details>
* Describe `fragment` lifecycle. What does it happen during screen rotation?
  <details>
  <summary>Answer</summary>
  
  The `onAttach()` callback is invoked when the fragment has been added to a `FragmentManager` and is attached to its host activity. At this point, the fragment is active, and the `FragmentManager` is managing its lifecycle state.
  
  The `onDetach()` callback is invoked when the fragment has been removed from a `FragmentManager` and is detached from its host activity. The fragment is no longer active and can no longer be retrieved using `findFragmentById()`.
  
  Source: https://developer.android.com/guide/fragments/lifecycle
  </details>
* What's the difference between fragment lifecycle and fragment view lifecycle?
  <details>
  <summary>Answer</summary>
  
  Pic: https://developer.android.com/static/images/guide/fragments/fragment-view-lifecycle.png
  
  Source: https://developer.android.com/guide/fragments/lifecycle#states
  </details>
* What is `fragment manager`?
  <details>
  <summary>Answer</summary>
  
  The `FragmentManager` manages the fragment back stack. At runtime, the `FragmentManager` can perform back stack operations like adding or removing fragments in response to user interactions. Each set of changes are committed together as a single unit called a `FragmentTransaction`.
  
  Source: https://developer.android.com/guide/fragments/fragmentmanager
  </details>
* How can we transfer data between fragments?
  <details>
  <summary>Answer</summary>
  
  - Via shared `ViewModel`
  
  - Via arguments (bundle)
  
  - Using Fragment Result API
  
  Source: https://developer.android.com/guide/fragments/communicate
  </details>
* Why shouldn't we to use the fragment constructor to pass the data?
  <details>
  <summary>Answer</summary>
  
  By default, the `FragmentManager` uses a `FragmentFactory` that the framework provides to instantiate a new instance of your `fragment`. This default factory uses reflection to find and invoke a no-argument constructor for your `fragment`. This means that you can't use this default factory to provide dependencies to your `fragment`. It also means that any custom constructor you used to create your `fragment` the first time is not used during recreation by default.
  
  Source: https://developer.android.com/guide/fragments/fragmentmanager#dependencies
  </details>
* What is `target fragment`?
  <details>
  <summary>Answer</summary>
  
  Target fragment is used for setting result to calling fragment like `startActivityForResult`.
  </details>
* What is `retained fragment`? What are disadvantages?
  <details>
  <summary>Answer</summary>
  
  If we add the setting `setRetainInstance(true)` our fragment won't destroy when activity recreates.
  
  We should use it if our fragment is without view. Otherwise it can hold references on activity what triggers memory leaks.
  
  This method is deprecated. 
  </details>
* How can `activity` and `fragment` interact?
  <details>
  <summary>Answer</summary>
  
  - Via shared `ViewModel`
  
  - Via `interface`
  </details>
* What’s the difference between `replace()` and `add()` methods in `fragment manager`?
  <details>
  <summary>Answer</summary>
  
  `add()` method keeps on adding fragments on top of the previous fragment in `FragmentContainer`.

  While `replace()` methods clears all the previous Fragment from Containers and then add it in `FragmentContainer`.
  </details>
* What's the difference between `commit()`, `commitNow()` and `commitAllowingStateLoss()`?
  <details>
  <summary>Answer</summary>
  
  Calling `commit()` doesn't perform the transaction immediately. Rather, the transaction is scheduled to run on the main UI thread as soon as it is able to do so. If necessary, however, you can call `commitNow()` to run the fragment transaction on your UI thread immediately.

  Note that `commitNow` is incompatible with `addToBackStack`. Alternatively, you can execute all pending `FragmentTransactions` submitted by `commit()` calls that have not yet run by calling `executePendingTransactions()`. This approach is compatible with `addToBackStack`.

  For the vast majority of use cases, `commit()` is all you need.
  </details>
* How would work the back button if previous fragments were added within one transaction?
  <details>
  <summary>Answer</summary>
  If you added or removed multiple fragments within a single transaction, all of those operations are undone when the back stack is popped.
  
  Source: https://developer.android.com/guide/fragments/fragmentmanager
  </details>
* Can we put fragments into each other?
  <details>
  <summary>Answer</summary>
  
  Yes. Fragments are capable of hosting one or more child fragments. Inside a fragment, you can get a reference to the `FragmentManager` that manages the fragment's children through `getChildFragmentManager()`. If you need to access its host FragmentManager, you can use `getParentFragmentManager()`.
  
  Source: https://developer.android.com/guide/fragments/fragmentmanager
  </details>
* How to support multiple back stacks?
  <details>
  <summary>Answer</summary>
  
  In some cases, your app might need to support multiple back stacks. A common example is if your app uses a bottom navigation bar. `FragmentManager` allows you to support multiple back stacks with the `saveBackStack()` and `restoreBackStack()` methods. These methods allow you to swap between back stacks by saving one back stack and restoring a different one.
  
  `saveBackStack()` works similarly to calling `popBackStack()` with the optional name parameter: the specified transaction and all transactions after it on the stack are popped. The difference is that `saveBackStack()` saves the state of all fragments in the popped transactions.
  </details>
    
#### Service
* What is `Service`? What are different types of services?
  <details>
  <summary>Answer</summary>
  
  A `Service` is an application component that can perform long-running operations in the background. It does not provide a user interface. Once started, a service might continue running for some time, even after the user switches to another application. Additionally, a component can bind to a service to interact with it and even perform interprocess communication (`IPC`). For example, a service can handle network transactions, play music, perform file I/O, or interact with a content provider, all from the background.
    
  Source: https://developer.android.com/guide/components/services
  </details>
* What `service` types do you know?
  <details>
  <summary>Answer</summary>
  
  - **Foreground**. 
    
    It performs some operation that is noticeable to the user. For example, an audio app would use a foreground service to play an audio track. Foreground services must display a Notification. This notification cannot be dismissed unless the service is either stopped or removed from the foreground. Foreground services continue running even when the user isn't interacting with the app.

  - **Background**. A background service performs an operation that isn't directly noticed by the user. For example, if an app used a service to compact its storage, that would usually be a background service. 
    
  - **Bound**. A service is bound when an application component binds to it by calling `bindService()`. A bound service offers a client-server interface that allows components to interact with the service, send requests, receive results, and even do so across processes with interprocess communication (`IPC`). A bound service runs only as long as another application component is bound to it. Multiple components can bind to the service at once, but when all of them unbind, the service is destroyed.
    
  Source: https://developer.android.com/guide/components/services#Types-of-services
  </details>
* How would you choose between `Thread` and `Service`?
  <details>
  <summary>Answer</summary>
  
  A `service` is simply a component that can run in the background, even when the user is not interacting with your application.
    
  If you must perform work outside of your main thread, but only while the user is interacting with your application, you should instead create a new `thread` in the context of another application component.
    
  Source: https://developer.android.com/guide/components/services#Choosing-service-thread
  </details>
* What's the difference between bound and unbound service?
  <details>
  <summary>Answer</summary>
  
  - Bound service. 
    
    The service is created when another component (a client) calls `bindService()`. The client then communicates with the service through an `IBinder` interface. The client can close the connection by calling `unbindService()`. Multiple clients can bind to the same service and when all of them unbind, the system destroys the service. The service does not need to stop itself.
    
  - Unbound service.
    
    The service is created when another component calls startService(). The service then runs indefinitely and must stop itself by calling stopSelf(). Another component can also stop the service by calling stopService(). When the service is stopped, the system destroys it.
    
  Picture of lifecycle: https://developer.android.com/static/images/service_lifecycle.png
  
  Source: https://developer.android.com/guide/components/services#Lifecycle
  </details>
* What should return `onStartCommand()` method and what does it mean?
  <details>
  <summary>Answer</summary>
  
  It should return one of these constants:
    
  - `START_NOT_STICKY`. If the system kills the service after `onStartCommand()` returns, do not recreate the service unless there are pending intents to deliver. This is the safest option to avoid running your service when not necessary and when your application can simply restart any unfinished jobs.
    
  - `START_STICKY`. If the system kills the service after `onStartCommand()` returns, recreate the service and call `onStartCommand()`, but *do not redeliver the last intent*. Instead, the system calls `onStartCommand()` with a null intent unless there are pending intents to start the service. In that case, those intents are delivered. This is suitable for media players (or similar services) that are not executing commands but are running indefinitely and waiting for a job.
    
  - `START_REDELIVER_INTENT`. If the system kills the service after `onStartCommand()` returns, recreate the service and call `onStartCommand()` *with the last intent* that was delivered to the service. Any pending intents are delivered in turn. This is suitable for services that are actively performing a job that should be immediately resumed, such as downloading a file.
    
  Source: https://developer.android.com/guide/components/services#ExtendingService
  </details>
* Which context can we use to start `service`?
  <details>
  <summary>Answer</summary>
  
  We can use both. 
  </details>
* Can we show `toast` from `service`? 
  <details>
  <summary>Answer</summary>
  
  Yes. But since the toast works only with main thread we need to use Handler to show Toast from Service.
  </details>

#### Content Provider
* What is Content provider?
  <details>
  <summary>Answer</summary>
  
  Content providers can help an application manage access to data stored by itself, stored by other apps, and provide a way to share data with other apps. They encapsulate the data, and provide mechanisms for defining data security. Content providers are the standard interface that connects data in one process with code running in another process.
  
  Source: https://developer.android.com/guide/topics/providers/content-providers
  </details>
* What should we do if we want to share our app's data via `ContentProvider`?
  <details>
  <summary>Answer</summary>
  
  When you want to access data in a content provider, you use the `ContentResolver` object in your application's `Context` to communicate with the provider as a client. The `ContentResolver` object communicates with the provider object, an instance of a class that implements `ContentProvider`. The provider object receives data requests from clients, performs the requested action, and returns the results. This object has methods that call identically-named methods in the provider object, an instance of one of the concrete subclasses of `ContentProvider`. The `ContentResolver` methods provide the basic "CRUD" (create, retrieve, update, and delete) functions of persistent storage.
  
  Source: https://developer.android.com/guide/topics/providers/content-provider-basics#ClientProvider
  </details>
    
#### Broadcast Receiver
* What is a broadcast?
  <details>
  <summary>Answer</summary>
  Android apps can send or receive broadcast messages from the Android system and other Android apps, similar to the publish-subscribe design pattern. 
    
  These broadcasts are sent when an event of interest occurs. For example, the Android system sends broadcasts when various system events occur, such as when the system boots up or the device starts charging. Apps can also send custom broadcasts, for example, to notify other apps of something that they might be interested in (for example, some new data has been downloaded).

  Apps can register to receive specific broadcasts. When a broadcast is sent, the system automatically routes broadcasts to apps that have subscribed to receive that particular type of broadcast.

  Source: https://developer.android.com/guide/components/broadcasts
  
  </details>
* What are the types of broadcast receivers do you know?
  <details>
  <summary>Answer</summary>
  
  - Manifest-declared receivers.
  
  If you declare a broadcast receiver in your manifest, the system launches your app (if the app is not already running) when the broadcast is sent.
  
  *Note:* If your app targets API level 26 or higher, you cannot use the manifest to declare a receiver for implicit broadcasts (broadcasts that do not target your app specifically), except for a few implicit broadcasts that are exempted from that restriction. In most cases, you can use scheduled jobs instead.
  
  - Montext-registered receivers.
  
  Context-registered receivers receive broadcasts as long as their registering context is valid. For an example, if you register within an `Activity` context, you receive broadcasts as long as the activity is not destroyed. If you register with the Application context, you receive broadcasts as long as the app is running.
  </details>
* What is a `LocalBroadcastManager`?
  <details>
  <summary>Answer</summary>
  
  For obvious reasons, global broadcasts must never contain sensitive information. You can, however, broadcast such information locally using the `LocalBroadcastManager` class, which is a part of the Android Support Library.

  The `LocalBroadcastManager` is much more efficient as it doesn’t need inter-process communication.

  Below are some of its benefits:

  - Broadcast data won’t leave your app, so don’t need to worry about leaking private data.
  
  - It is not possible for other applications to send these broadcasts to your app, so you don’t need to worry about having security holes they can exploit.
  
  - It is more efficient than sending a global broadcast through the system.
  
  - No overhead of system-wide broadcast.
  </details>
* What restrictions does `BroadcastReceiver` have?
  <details>
  <summary>Answer</summary>
  
  - Android 9
    
  Beginning with Android 9 (API level 28), The `NETWORK_STATE_CHANGED_ACTION` broadcast doesn't receive information about the user's location or personally identifiable data.

  In addition, if your app is installed on a device running Android 9 or higher, system broadcasts from Wi-Fi don't contain SSIDs, BSSIDs, connection information, or scan results. To get this information, call `getConnectionInfo()` instead.

  - Android 8.0
  
  Beginning with Android 8.0 (API level 26), the system imposes additional restrictions on manifest-declared receivers.

  If your app targets Android 8.0 or higher, you cannot use the manifest to declare a receiver for most implicit broadcasts (broadcasts that don't target your app specifically). You can still use a context-registered receiver when the user is actively using your app.

  - Android 7.0
  
  Android 7.0 (API level 24) and higher don't send the following system broadcasts:

  `ACTION_NEW_PICTURE`
  
  `ACTION_NEW_VIDEO`
  
  Also, apps targeting Android 7.0 and higher must register the `CONNECTIVITY_ACTION` broadcast using `registerReceiver(BroadcastReceiver, IntentFilter)`. Declaring a receiver in the manifest doesn't work.
  
  Source: https://developer.android.com/guide/components/broadcasts#changes-system-broadcasts
  </details>

#### Intent
* What is `Intent`?
  <details>
  <summary>Answer</summary>
  
  An `Intent` is a messaging object you can use to request an action from another app component. Although intents facilitate communication between components in several ways, there are three fundamental use cases:
  
  - Starting an `activity`

  - Starting a `service`
  
  - Delivering a `broadcast`
  
  Source: https://developer.android.com/guide/components/intents-filters
  </details>
* What `Intent` types do you know?
  <details>
  <summary>Answer</summary>
    
  - **Explicit intents**. Specify which application will satisfy the intent, by supplying either the target app's package name or a fully-qualified component class name. You'll typically use an explicit intent to start a component in your own app, because you know the class name of the activity or service you want to start. For example, you might start a new activity within your app in response to a user action, or start a service to download a file in the background.
  
  - **Implicit intents**. Do not name a specific component, but instead declare a general action to perform, which allows a component from another app to handle it. For example, if you want to show the user a location on a map, you can use an implicit intent to request that another capable app show a specified location on a map.
  
  
  Source: https://developer.android.com/guide/components/intents-filters#Types
  </details>
* What is `IntentFilter`? 
  <details>
  <summary>Answer</summary>
  
  To advertise which implicit intents your app can receive, declare one or more intent filters for each of your app components with an `<intent-filter>` element in your manifest file. Each intent filter specifies the type of intents it accepts based on the intent's action, data, and category. The system delivers an implicit intent to your app component only if the intent can pass through one of your intent filters.
  
  Inside the `<intent-filter>`, you can specify the type of intents to accept using one or more of these three elements:

  - `<action>`. Declares the intent action accepted, in the `name` attribute. The value must be the literal string value of an action, not the class constant.
  
  - `<data>`. Declares the type of data accepted, using one or more attributes that specify various aspects of the data `URI` (`scheme`, `host`, `port`, `path`) and MIME type.

  - `<category>`. Declares the intent category accepted, in the `name` attribute. The value must be the literal string value of an action, not the class constant.
  
  Source: https://developer.android.com/guide/components/intents-filters#Receiving
  </details>
* What is `PendingIntent` in Android?
  <details>
  <summary>Answer</summary>
  
  A `PendingIntent` object is a wrapper around an `Intent` object. The primary purpose of a `PendingIntent` is to grant permission to a foreign application to use the contained `Intent` as if it were executed from your app's own process.
  
  Major use cases for a pending intent include the following:

  - Declaring an `intent` to be executed when the user performs an action with your `Notification`
  
  - Declaring an `intent` to be executed when the user performs an action with your `App Widget`
  
  - Declaring an `intent` to be executed at a specified future time (the Android system's `AlarmManager` executes the `Intent`).
  
  Source: https://developer.android.com/guide/components/intents-filters#PendingIntent
  </details>
* What are restrictions around `PendingIntent`?
  <details>
  <summary>Answer</summary>
  
  If your app targets Android 12 or higher, you must specify the mutability of each PendingIntent object that your app creates. To declare that a given PendingIntent object is mutable or immutable, use the `PendingIntent.FLAG_MUTABLE` or `PendingIntent.FLAG_IMMUTABLE` flag, respectively.

  If your app attempts to create a PendingIntent object without setting either mutability flag, the system throws an `IllegalArgumentException`
  
  In most cases, your app should create immutable `PendingIntent` objects. If a `PendingIntent` object is immutable, then other apps cannot modify the intent to adjust the result of invoking the intent.

  Source: https://developer.android.com/guide/components/intents-filters#DeclareMutabilityPendingIntent
  </details>
* When should we use mutable `PendingIntent`?
  <details>
  <summary>Answer</summary>
  
  - Supporting direct reply actions in notifications. The direct reply requires a change to the clip data in the PendingIntent object that's associated with the reply.
  
  - Associating notifications with the Android Auto framework, using instances of `CarAppExtender`.

  - Placing conversations in bubbles using instances of `PendingIntent`. A mutable `PendingIntent` object allows the system to apply the correct flags, such as `FLAG_ACTIVITY_MULTIPLE_TASK` and `FLAG_ACTIVITY_NEW_DOCUMENT`.
  
  - Requesting device location information by calling `requestLocationUpdates()` or similar APIs. The mutable PendingIntent object allows the system to add intent extras that represent location lifecycle events. These events include a change in location and a provider becoming available.

  - Scheduling alarms using `AlarmManager`. The mutable `PendingIntent` object allows the system to add the `EXTRA_ALARM_COUNT` intent extra. This extra represents the number of times that a repeating alarm has been triggered. By containing this extra, the intent can accurately notify an app as to whether a repeating alarm was triggered multiple times, such as when the device was asleep.

  </details>

#### Data saving
* How can we persist any data in an Android app? 
* Describe how `Scoped Storage` works in Android.
* What is `SharedPreferences`?
* What's the difference of`commit()` and `apply()` in `SharedPreferences?
* How to encrypt data in Android?

#### Memory
* What is the `onTrimMemory()` method? 
* Why does the `OutOfMemoryError` happen?
* How we can find memory leaks in Android app?

#### Push Notifications
* How can we handle push notifications?
* What is Firebase `topic`?
* What is push `channel`?
* What is Firebase `token`?
* What is push `category`?

#### UI
* What’s the difference between `View` and `ViewGroup`?
  <details>
  <summary>Answer</summary>
  
  - View
    - View objects are the basic building blocks of User Interface(UI) elements in Android.
    - View is a simple rectangle box which responds to the user's actions. Examples are EditText, Button, CheckBox etc..
    - View refers to the android.view.View class, which is the base class of all UI classes.
  - ViewGroup
    - ViewGroup is the invisible container. It holds View and ViewGroup. For example, LinearLayout is the ViewGroup that contains Button(View), and other Layouts also.
    - ViewGroup is the base class for Layouts.

  Source: https://stackoverflow.com/a/34676816/7041761
  </details>
 
* What is `ViewPager`? Is it `View` or `ViewGroup`?
  <details>
  <summary>Answer</summary>
  
  `ViewPager` is `ViewGroup`.

  It's usually used for displaying Views of Fragments in a swipeable format.
  </details>
* When should we use `FrameLayout`, `LinearLayout` or `ConstraintLayout`?
  <details>
  <summary>Answer</summary>

  - With Complex UI where we can have more hierarchies, it is wise to use `ConstraintLayout`.
 
  - If you are using `LinearLayout` with weights/`RelativeLayout` with hierarchies, replace them with `ConstraintLayout`.
 
  - For simple layouts with just one view centred on the screen, go for `FrameLayouts`.
 
  - For simple screens, where you have to place views just horizontally and vertically, go for `LinearLayout`.

  Source: https://nik-arora8059.medium.com/a-battle-towards-performance-constraintlayout-vs-other-layouts-part-3-d7646a849b4e
  </details>

* What ways can we implement `Splash Screen`?
  <details>
  <summary>Answer</summary>

  The official way is to use Splash Screen API.

  Source: https://developer.android.com/develop/ui/views/launch/splash-screen
  </details>

* What is a `resources` directory?
  <details>
  <summary>Answer</summary>

  Resources are the additional files and static content that your code uses, such as bitmaps, layout definitions, user interface strings, animation instructions, and more.

  You can add there following files:

  - `animator/`. XML files that define Property animations.
 
  - `anim/`. XML files that define Tween animations. Property animations can also be saved in this directory, but the `animator/` directory is preferred for property animations to distinguish between the two types.
 
  - `color/`. XML files that define a state list of colors. For more information, see Color state list resource.
 
  - `drawable/`. Bitmap files (PNG, .9.png, JPG, or GIF) or XML files that are compiled into the following drawable resource subtypes:

    - Bitmap files

    - Nine-patches (re-sizable bitmaps)

    - State lists

    - Shapes

    - Animation drawables

    - Other drawables
 
  - `mipmap/`. Drawable files for different launcher icon densities.
 
  - `layout/`. XML files that define a user interface layout.
 
  - `menu/`. XML files that define app menus, such as an options menu, context menu, or submenu.
 
  - `raw/`. XML files that define Property animations. Arbitrary files to save in their raw form. To open these resources with a raw InputStream, call Resources.openRawResource() with the resource ID, which is R.raw.filename.

    However, if you need access to the original filenames and file hierarchy, consider saving resources in the `assets/` directory instead of `res/raw/`. Files in assets/ aren't given a resource ID, so you can only read them using AssetManager.
 
  - `values/`. XML files that contain simple values, such as strings, integers, and colors.
 
  - `xml/`. Arbitrary XML files that can be read at runtime by calling Resources.getXML(). Various XML configuration files must be saved here.
 
  - `font/`. Font files with extensions such as TTF, OTF, or TTC, or XML files that include a <font-family> element.

  Source: https://developer.android.com/guide/topics/resources/providing-resources
  </details>
  
* Why should we put strings and dimens into resources files?
  <details>
  <summary>Answer</summary>

  What about strings, it's recommended to use `strings.xml` because:
  - It's much easier to maintain strings code
  
  - There's native approach to make strings translations
 
  - To make code cleaner
 
  What about dimens, all about supporting different screen sizes.

  Source: https://developer.android.com/develop/ui/views/launch/splash-screen
  </details>
  
* What are `weight` and `orientation` in `LinearLayout`? What if we ignore `orientation`?  
* `ConstraintLayout`: what are `bias`, `barrier`, `chain`, `guideline`.
* How can we maintain different screen sizes?
* What’s the difference between `dp` vs `sp`?
* Why is it better to use vector images?
* What are `include` and `merge` tags in xml?
* What’s the difference between `DataBinding` и `ViewBinding`?
* What is `Window`? Can application has one or multiple Window?
* What need we do for touches and gestures overriding?
* Describe briefly how `RecyclerView` works.
* What two methods must we implement in `DiffUtil`? What do they mean?
* When should we use `CoordinatorLayout`?
* How do the Touch Control and Events work in Android?
* What is 9-patch image?

#### Custom views
* What's the difference between compound view and custom view?
* Describe lifecycle methods of `View`.
* What parameter should we handle in `onMeasure()`?
* How to redraw the custom view? What options do we have?
    
#### Network
* What is `REST`?
* What is `OkHttp`?
* What is `Retrofit`?
* What is `SSL`?
* How can we check internet connection?
* What is interceptor in `OkHttp`? Give examples of it.
* How would you handle token refreshing?
* What Http-methods do you know?
    
#### Application Processes
* What is application process?
* Can app work in multiple processes?
* What is `IPC`? 

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

#### RxJava
* Describe the reactive approach.
* What is scheduler in `RxJava`?
* What’s the difference between `IO` and `Computation` scheduler? Is there any clear separation?
* What are `subscribeOn` and `observeOn`? Is their order in chain important?
* What `source types` do you know? 
* What’s the difference between `cold` and `hot` source? 
* What’s the difference between `Observable` and `Flowable`?
* What is `backpressure`?
* What is backpressure strategy? 
* What’s the difference between `debounce` and `distinctUntilChanged`?
* What’s the difference between `map` and `flatmap`?
* How can we implement searching with these requirements: a) limit network requests with 500ms of idle; b) prevent network requests of similar strings.
* What is `Subject`? What types of this do you know?
* What `subject` is `livedata` approach similar with?
* What ways of error handling do you know?
* Does `zip` operator acts in parallel or sequentially?

#### Coroutines
* What is `Coroutine`?
  <details>
  <summary>Answer</summary>
    
  A coroutine is an instance of suspendable computation. It is conceptually similar to a thread, in the sense that it takes a block of code to run that works concurrently with the rest of the code. However, a coroutine is not bound to any particular thread. It may suspend its execution in one thread and resume in another one.

  Coroutines can be thought of as light-weight threads, but there is a number of important differences that make their real-life usage very different from threads.
    
  Coroutines are less resource-intensive than JVM threads. Code that exhausts the JVM's available memory when using threads can be expressed using coroutines without hitting resource limits
    
  Source: https://kotlinlang.org/docs/coroutines-basics.html
  </details>
* What is `Continuation`?
  <details>
  <summary>Answer</summary>
    
  Code block inside a coroutine compiles into separate java class named `Continuation`.
    
  `Continuation` is like a callback for `suspend` functions.
    
  The main goal of `continuation` is to assure that the code after `suspend` functions will be invoked only after `suspend` was finished.
    
  Every `suspend` function has the `Continuation` reference. After `suspend` was finished it executes `invokeSuspend()` function of `Continuation`.
  </details>
* What is `Coroutine Context`?
  <details>
  <summary>Answer</summary>
    
  That is a context where is coroutine works.
    
  It consists of following parts:
    
  - Job
    
  - Dispatcher  
  
  - Exception Handler
    
  - Coroutine name
  </details>
* What is `Job`?
  <details>
  <summary>Answer</summary>
  
  Job is one of the most important coroutine objects. 
  
  It provides following opportunities: 
  
  - Keeps coroutine state (active/cancelled/finished)
  
  - Cancel coroutine
  
  - Start postponed coroutine
  
  When `Continuation` finishes `invokeSuspend` execution, it reports this to the `Job` which changes coroutine state.
  </details>
* What is `Scope`?
  <details>
  <summary>Answer</summary>
  
  The `Scope` is a mandatory component of coroutine creation process.
    
  It is a wrapper of the `CoroutineContext`. We use it for uniting all coroutines. It has `Job` which is a parent for every child coroutines.
  </details>
* Where can we get `Scope`?
  <details>
  <summary>Answer</summary>
    
  - `ViewModel` component (from Jetpack). It has `viewModelScope` property. 
  
    All coroutines will be cancelled during `ViewModel` finishing.
  
  - `LifecycleScope` which defined for each `Lifecycle` object. 
  
    Any coroutine launched in this scope is canceled when the `Lifecycle` is destroyed. 
    
    You can access the `CoroutineScope` of the `Lifecycle` either via `lifecycle.coroutineScope` or `lifecycleOwner.lifecycleScope` properties
  </details>
* What is `GlobalScope`?
  <details>
  <summary>Answer</summary>
    
  This scope doesn't have any `Job`. So you can't cancel coroutines of this scope. All coroutines of this scope will work until self-stop or process end.
  
  *Note:* it can cause memory leakes.
  </details>
  
* How can we cancel `CoroutineScope`?
  <details>
  <summary>Answer</summary>
    
  We need to execute `CoroutineScope.cancel()`. By this action we cancel parent `Job` and it cancels all coroutines `Job` which have been created inside this `CoroutineScope`. 
  </details>
* What is structured concurrency?
  <details>
  <summary>Answer</summary>
    
  It is a mechanism of hierarchical structure for organizing coroutines work. 
  
  It describes these three main principles:
  
  1. If you cancel `Scope` - you cancel it's coroutines too. 
  
  2. `Scope` knows about all it's coroutines. It works because of `Job` relations parent-child.
  
  3. `Scope` waits all child coroutines. But `Scope` can work longer that all it's child coroutines.
  </details>
* What is `Dispatcher`?
  <details>
  <summary>Answer</summary>
    
  It determines what thread or threads the corresponding coroutine uses for its execution. The coroutine dispatcher can confine coroutine execution to a specific thread, dispatch it to a thread pool, or let it run unconfined.

  </details>
* How can we cancel all coroutines of `CoroutineScope` but keep `CoroutineScope` alive?
  <details>
  <summary>Answer</summary>
    
  We need to get a `Job` of the `CoroutineScope` and execute `cancel()` function.
  </details>
* How can we change dispatcher inside coroutine?
  <details>
  <summary>Answer</summary>
    
  We can use `withContext(dispatcher)`
  </details>
* What we can use `runBlocking` for?
* What is `Channel`?
  <details>
  <summary>Answer</summary>
    
  `Channel` was added as an inter-coroutine communication primitive. Channels support one-to-one, one-to-many, many-to-one, and many-to-many communication between coroutines, and every value that is sent to the channel is received once.

  You cannot use channels to distribute events or state updates in a way that allows multiple subscribers to independently receive and react upon them.

  Source: https://elizarov.medium.com/shared-flows-broadcast-channels-899b675e805c
  </details>
* What is `Flow`? Is it cold or hot by default?
  <details>
  <summary>Answer</summary>
    
  Flows are typically cold — a Flow<Value> created by `flow { … }` builder function is a passive entity. Consider the following code:

  ```
  val coldFlow = flow {
    while (isActive) {
        emit(nextEvent)
    }
  }
  ```

  The flow itself is not backed by any kind of computation and does not have any state by itself until it starts to be collected. Every collector coroutine executes its own instance of emitting code.
  
  Source: https://elizarov.medium.com/shared-flows-broadcast-channels-899b675e805c
  </details>
* What's the difference between `SharedFlow` and `StateFlow`?
* What is `CallbackFlow`? 
* What do you know about semaphore and mutex in coroutines?


## Dagger
* What is `dependencies graph`?
* What are Dagger `component`, `module` and `subcomponent`?
* What's the difference between `@Binds` and `@Provides`?
* How we can create the `component`?
* How to `inject` values at runtime in Dagger?
* What is `scope` in Dagger?
* How does the `scope` knows that it should be closed?
* How we can create our own `scope`?
* How to implement Dagger in multi module architecture?

## Database
* What's the difference between NoSql and Sql approaches?
* What's the difference between `inner join` and `join`?
* Which approaches do you know in Android?
* How would you choose between `Realm` and `Room`?
* How would you resolve the migration issue in Room?
* What is `ORM`?

## Architecture

* What's the difference between `MVC`, `MVVM`, `MVP`, `MVI` approaches? Which are the most popular right now and why? 
* How would you choose between `MV`-approaches?
* What is `SOLID`? Describe its' principles.
* What are `KISS` and `DRY` principles?
* What is `god object` and what examples in Android SDK do you know?
* What's the difference between `dependency injection`, `dependency inversion` and `inversion of control`?
* Describe `Clean Architecture` and decompose it on layers.
* Describe `Single Activity` principle.
* What is singleton? What pros and cons do you know?
* What is `multi module` architecture? Tell about pros and cons.
* Describe 3 main principles of `OOP`.
* What’s the difference between `inheritance` and `composition`?
* What's the difference between `abstract factory` and `factory pattern`?
* How would you implement a download feature to prevent resetting on configuration changing without `DownloadManager` usage?
