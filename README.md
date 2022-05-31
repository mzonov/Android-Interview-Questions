### Java

* What is Object? What methods of this do you know?
* What does equals() method do. What is the difference with “==” statement.
* Why do you need hashCode()?
* What is the relationship between hashCode() and equals()?
* How are hasCode() and equals() implemented?
* What’s wrong if we override only equals() without hashCode?
* What access modifiers do you know?
* Which access modifier is more strict: protected or package-private?
* What does “final” keyword mean?
* Does it make any sence to declare method private final?
* What if we declare the only constructor as final?
* What does static keyword mean?
* Can we overload static method?
* What is static class? When should we use it?
* What class types do you know?
* How can we get access from inner class to outer class?
* What exception types do you know? What are the differences?
* Name few classes at the top of exceptions ierarchy.
* What is Error? Examples?
* What construction we use for exception handling?
* Can we use try-finally only (without catch)?
* Imagine, we have try-finally block. In try-block was thrown exception and execution was moved to finally-block. In finally block an exception was thrown too. Which one exception would be ignored?
* Does finally block always triggered?
* Does exception catching order make any sence? E.g. which should be first: IOException or FileNotFoundException?
* What is Java Reflection? 
* What’s the difference between = new String() и = “ “?
* Is String mutable type or not? Why?
* What is Java String Pool?
* What is String.intern() method?
* What’s the difference between String, StringBuilder and StringBuffer.
* Why is it said that the length() method of String class doesn't return accurate results?
* What is type erasing?
* What’s the difference between overloading and overriding?
* What is JIT-compiler?
* What is ClassLoader?
* What’s the difference between abstract class and interface?

### Java Memory Model

* What are the differences between Heap and Stack?
* What is a Memory Leak?
* How do you identify a Memory Leak in Android?
* Describe briefly how GC works.
* What reference types do you know? What are the differences between them?

### Collections (Java&Kotlin both)

* What is Comparator?
* What’s the difference between plain array and list?
* What’s the difference between ArrayList and LinkedList?
* Describe collections tree.
* What is Map? Describe Map tree.
* How does HashMap work?
* What are Generics? What are their advantages?
* What is the main feature of TreeMap or TreeSet?

### Kotlin

* Tell me 5 features of Kotlin.
* What’s the difference between val and var keyword?
* Describe Kotlin access modifiers? Which one is default?
* What are let, run, also, apply, with methods?
* What are infix functions? 
* How can we create constant?
* What are the differsences between sequence and collections approaches? 
* What’s the difference between nested and inner classes?
* What is smart cast?
* What’s the difference between Kotlin Any and Java Object?
* What are «?» and «!!» signs?
* What’s the problem with usage of Java classes in kotlin?
* Are Kotlin exceptions different from Java exceptions?
* What is Nothing type?
* What are extensions?
* What is data class? What’s the difference between this and plain java class? 
* What is sealed classs? How is it different from Enum? What is sealed class under the hood?
* What is covariance and contravariance? 
* What’s the difference between «==» and «===» comparing?
* What’s the difference between is and as operators?
* How can we create singleton in Kotlin?
* How can we create anonymous class?
* What is delegate?
* What are inline/crossinline/noinline keywords? Maybe we should inline keyword everywhere?
* What is SAM-interface?
* What’s the difference between postValue() and setValue() in mutableLiveData? 
* What is typealias?
* When should we use lazy method? 
* What’s the difference between property and field?
* What is backing field?
* What is destructuring declarations?
* What is reified keyword? How does it work?
* What does annotation @JvmOverloads mean?
* What is TypeArray? How does it work?

### Android. Core
* What are Activity and Fragment? What’s the difference between them?
* What’s the difference between appContext and activity context? 
* How can we launch activity and fragment? 
* Describe lifecycle of activity and fragment (+ during screen rotation).
* What are tasks and backstack.
* How can we transfer data between activities?
* What’s the difference between Serializable and Parcelable?
* Which Activity’s lifecycle method triggers during Dialog creation?
* What is TargetFragment?
* What is retain fragment?
* What is ViewPager? Is it View or ViewGroup? 
* What are runtime permissions? 
* What is Intent? What types of Intent do you know?
* What is IntentFilter? 
* What is Pending Intent in Android?
* What are different launch modes available in Android?
* How can activity and fragment interact?
* How can we transfer data between fragments?
* In which case the lifecycle methods call chain would be like this: onCreate() -> onDestroy()?
* When fragment’s setRetain() method doesn’t work?
* What’s the difference in addToBackStack between replace() and add() methods?
* Can app work in multiple processes?
* What is Service? What are different types of services?
* Bound Service vs UnBounded service.
* How to start a Foreground Service
* What is Sticky Intent in Android?
* What is Content Provider?
* Can Content Provider be started before Application?
* What is JIT-compiler? What are advantages and disadvantages?
* How does the main thread work?
* Can any Android component be launched before Application-component?
* What are the differences between commit, commitNow and commitAllowingStateLoss?
* Can we put fragments into each other?
* What is IPC? 
* Explain the AndroidManifest.xml file and why do you need this?
* What is ANR? How to prevent it?
* How to reduce your app size?
* What is Wake Lock?
* What is Strict mode?
* What is AIDL?

### Android. UI
* What’s the difference between View and ViewGroup? 
* When should we use FrameLayout, LinearLayout or ConstraintLayout?
* What ways can we implement SplashScreen?
* What are resources?
* Why should we put strings and dimens into resources files?
* What are weight and orientation in LinearLayout? What is affect without orientation?
* ConstraintLayout: what are vertical/horizontal bias, barrier, chain, guideline.
* How can we maintain different screen sizes?
* What’s the difference between dp vs sp?
* Why is it better to use vector images?
* What are include and merge tags in xml?
* What’s the difference between DataBinding и ViewBinding?
* What is Window? Can application has one or multiple Window?
* Tell me about main lifecycle methods of View.
* What parameter should we handle in onMeasure()?
* What need we do for touches and gestures overriding?
* Describe briefly how RecyclerView works.
* When should we use CoordinatorLayout?

### Multithreading
* What are actual and deprecated ways of multithreading implementation in Android development?
* What are Thread and Runnable?
* What’s the difference Thread.stop() and Thread.interrupt()?
* What are mutex and semaphore?
* Why do we need volatile?
* What is atomic operation? Examples?
* Which classes in Java can handle atomic operations?
* Is it thread safely to increment volatile variable?
* What is deadlock? How to prevent?
* What is liveLock? How to prevent?
* What is race condition? How to prevent?
* How can we manage threads work?
* What is double check lock? Usage example?
* What is WorkManager?
* What thread does GC use for garbage collection?
* What does syhcronized keyword do?
* What is used as mutex in synchronized method/block?
* What does volatile keyword do?
* What is the Object.wait() method? 
* Imagine that in run-method was thrown RuntimeException which hadn’t been catched. What would happen with thread? Is it any way to know about this Exception? Could we resume thread work?
* What is “happens before” relationship?
* When to use an Android service and when to use a thread

### RxJava
* Describe the reactive approach.
* What are subscribeOn and observeOn? Is their order in chain important?
* What is scheduler in RxJava?
* What’s the difference between IO and computation scheduler?
* What source types do you know? 
* What’s the difference between cold and hot source? 
* What’s the difference between Observable and Flowable?
* What is backpressure?
* What is backpressure strategy? 
* What’s the difference between debounce and distinctUntilChanged?
* What’s the difference between map and flatmap?
* How can we implement searching with these requirements: a) limit network requests with 500ms of idle; b) prevent network requests of similar strings.
* What is Subject? What types of this do you know?
* What ways of error handling do you know?
* Does Zip acts in parallel or sequentially?


### Architecture

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

### Android. Network

* What is REST?
* What is OkHttp?
* What is Retrofit?
* What is SSL?
* How can we check internet connection?
* What is interceptor in OkHttp? Give examples of it.
* How would you handle token refreshing?
* What Http-methods do you know?
