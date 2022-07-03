## Java


#### Object
* What is `Object`? What methods of this do you know?
* What does `equals()` method do. What is the difference with `==` statement.
* Why do you need `hashCode()`?
* What is the relationship between `hashCode()` and `equals()`?
* How are `hasCode()` and `equals()` implemented?
* What’s wrong if we override only `equals()` without `hashCode()`?

#### Exceptions
* What exception types do you know? What are the differences?
* Name few classes at the top of exceptions ierarchy.
* What is `Error`? Examples?
* What construction we use for exception handling?
* Can we use `try-finally` only (without `catch`)?
* Imagine, we have `try-finally` block. In `try`-block was thrown exception and execution was moved to `finally`-block. In `finally`-block an exception was thrown too. Which one exception would be ignored?
* Does `finally`-block always triggered? Is there any case when `finally` will not be executed?
* Does exception catching order make any sence? E.g. which should be first: `IOException` or `FileNotFoundException`?
* How we can create custom exception?

#### Modifiers & keywords
* What access modifiers do you know?
* Which access modifier is more strict: protected or package-private?
* What does `final` keyword mean?
* Does it make any sence to declare method private final?
* What if we declare the only constructor as final?
* What does static keyword mean?
* What class types do you know?
* How can we get access from inner class to outer class?

#### Static Components
* Which components can be marked as static?
* Can we override static method?
* What is static class? When should we use it? When shouldn't?
* What are the restrictions that are applied to the Java static methods?
* What is the static block?
* Can we make constructors static?
* Can we declare the static variables and methods in an abstract class?

#### Strings
* What’s the difference between `new String("value")` and `"value"`?
* Is String mutable type or not? Why?
* What is String Pool?
* What is `String.intern()` method?
* What’s the difference between `String`, `StringBuilder` and `StringBuffer`.
* Why is it said that the `length()` method of String class doesn't return accurate results?
* Why CharArray() is preferred over String to store the password?

#### Abstraction
* What is the abstraction?
* What’s the difference between abstract class and interface?
* Can there be an abstract method without an abstract class?
* Can the Interface be final? And abstract class?
* What is a marker interface?
* Can we define private and protected modifiers for the members in interfaces?

#### Nested and Inner classes
* What is a nested class?
* What is a inner class?
* What are the types of inner classes (non-static nested class) used in Java?
* Is there any difference between nested classes and inner classes?
* What are anonymous inner classes?
* What is the nested interface?

#### Multithreading
* Differentiate between process and thread?
* What are `Thread` and `Runnable`?
* What’s the difference `Thread.stop()` and `Thread.interrupt()`?
* What does `join()` method?
* Is it possible to start a thread twice?
* What are `Mutex` and `Semaphore`?
* Why do we need `volatile`?
* What does `sychronized` keyword do?
* What is atomic operation? Examples?
* Which classes in Java can handle atomic operations?
* Is it thread safely to increment `volatile` variable?
* What is deadlock? How to prevent?
* What is liveLock? How to prevent?
* What is race condition? How to prevent?
* How can we manage threads work?
* What is double check lock? Usage example?
* What thread does GC use for garbage collection?
* What is used as mutex in `synchronized` method/block?
* What is the `Object.wait()` method? 
* Why must `wait()` method be called from the synchronized block?
* Imagine that in run-method was thrown `RuntimeException` which hadn’t been catched. What would happen with thread? Is it any way to know about this Exception? Could we resume thread work?
* What is `happens before` relationship?
* What is `BlockingQueue`?
* What is the difference between Java Callable interface and Runnable interface?

#### Network
* Give a brief description of Java socket programming?
* What is Socket?
* What is Protobuf?
* What is WebSocket?
* What is WebRTC? 

#### Other
* What is `JIT-compiler`?
* What is `ClassLoader`?
* What is Java Reflection? When should we use it?
* What is a native method?
* What is an applet?


## Java Memory Model

* What are the differences between `Heap` and `Stack`?
* What is a Memory Leak?
* How do you identify a Memory Leak in Android?
* What is the Garbage Collector?
* How is garbage collection controlled?
* Describe briefly how GC works.
* How can an object be unreferenced?
* What is the purpose of the finalize() method?
* What reference types do you know? What are the differences between them?


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
* What is delegate?
* What are `inline`/`crossinline`/`noinline` keywords? Maybe we should inline keyword everywhere?
* What is `reified` keyword? How does it work?
* What is SAM-interface?
* What’s the difference between `postValue()` and `setValue()` in `mutableLiveData`? 
* What is backing field?
* What is destructuring declarations?
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
* What is covariance and contravariance? 
* What’s the difference between `==` and `===` comparing?
* What’s the difference between `is` and `as` operators?
* How can we create anonymous class?

#### Syntactic Sugar
* What is smart cast?
* What is `typealias` keyword?
* What are infix functions? 
* When should we make property `lazy`? 
* How can we create singleton in Kotlin?
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
* How to start a Foreground Service
* What is Sticky Intent in Android?
* What is `ContentProvider`?
* Can Content Provider be started before Application?
* What is JIT-compiler? What are advantages and disadvantages?
* How does the main thread work?
* Can any Android component be launched before Application-component?
* What are the differences between `commit`, `commitNow` and `commitAllowingStateLoss`?
* Can we put fragments into each other?
* What is IPC? 
* Explain the `AndroidManifest` file and why do you need this?
* What is ANR? How to prevent it?
* How to reduce your app size?
* What is Wake Lock?
* What is AIDL?
* What is a BroadcastReceiver?
* What is a LocalBroadcastManager?
* How does ViewModel work internally? 

#### Data saving
* How to persist data in an Android app? 
* What is ORM?
* How would you preserve Activity state during a screen rotation?
* Explain Scoped Storage in Android.
* How to encrypt data in Android?
* What is commit() and apply() in SharedPreferences?

#### Memory
* What is the `onTrimMemory()` method? 
* Why does the `OutOfMemory` happen?
* How we can find memory leaks in Android app?

#### Push Notifications
* How can we handle Push Notifications?
* What is Firebase `topic`?
* What is Push channel?
* What is Firebase token?

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
* What two methods must we implement in DiffUtil? What do they mean?
* When should we use `CoordinatorLayout`?
* How do the Touch Control and Events work in Android?

#### Network
* What is REST?
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
* What is UI-Automator?
* What testing libraries do you know?

#### Tools
* What is ADB?
* What is Strict mode?
* What is Android Lint?
* What is Multidex in Android?
* What does Android Studio Profiler help us to check?


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
* What source types do you know? 
* What’s the difference between cold and hot source? 
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

## Architecture

* What are the differences between MVVM, MVP, MVI approaches?.
* What is Moxy? What is the main feature of this?
* Describe SOLID principles.
* What is god object and what examples in Android SDK do you know?
* What are the differences between dependency injection, dependency inversion and control inversion?
* Describe Clean Architecture and decompose it on layers.
* Describe Single Activity principle.
* What is multi module architecture? What are advantages of this?
* Describe 3 main principles of OOP.
* What’s the difference between inheritance and composition?
* What's the difference between abstract factory and factory pattern?
