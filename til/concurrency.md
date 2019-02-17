

Concurrency is involved when more than one thread accesses an enity (class field) and one of them modifies its value.


How to ensure thread safety:
> 1. Don't share the state variable across threads;
> 2. Make the state variable immutable;
> 3. Use synchronization whenever accessing the state variable.

Peierls, Tim. Java Concurrency in Practice . Pearson Education. Kindle Edition. 


What is to be thread safe?
> Thread-safe code only manipulates shared data structures in a manner that ensures that all threads behave properly and fulfill their design specifications without unintended interaction. 
https://en.wikipedia.org/wiki/Thread_safety

or
> A class is thread-safe if it behaves correctly when accessed from multiple threads, regardless of the scheduling or interleaving of the execution of those threads by the runtime environment, and with no additional synchronization or other coordination on the part of the calling code.

Peierls, Tim. Java Concurrency in Practice . Pearson Education. Kindle Edition. 

or 
A code is considered thread safe if it behaves properly when accessed by multiple threads.

There is three level of thread safety
> 1. Thread safe: Implementation is guaranteed to be free of race conditions when accessed by multiple threads simultaneously.
> 2. Conditionally safe: Different threads can access different objects simultaneously, and access to shared data is protected from race conditions.
> 3. Not thread safe: Data structures should not be accessed simultaneously by different threads.

Race condition
A race condition is when the good behaviour of a piece of code relies on the good timing of multiple threads access. (To get lucky).

Re-entrancy
It means that locks are aquired on a per thread basis. So if a thread tries to access a lock that it holds, it will be sucesfull.


