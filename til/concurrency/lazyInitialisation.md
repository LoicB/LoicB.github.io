# Lazy Initialisation for Singleton

## Basic way
This solution is not thread safe.

```java
public class Something {
  private Something instace;
  
  private Something() {}
  
  public static Something getInstance() {
    if (instance == null) {
      instance = new Something();
    }
    return instance;
  }
}
```

## Using synchronisation
This solution is thread safe but expensive.

```java
public class Something {
  private Something instace;
  
  private Something() {}
  
  public synchronized static Something getInstance() {
    if (instace == null) {
      instance = new Something();
    }
    return instance;
  }
}
```

Every access to the instance will be synchronised, whislt only the first one needs to be.

## Double check
This solution is maybe thread safe.

```java
public class Something {
  private Something instance;
  
  private Something() {}
  
  public synchronized static Something getInstance() {
    if (instance == null) {
      synchronized (this) {
        if (instance == null) {
          instance = new Something();
        }
      }
    }
    return instance;
  }
}
```
[Here]{https://www.cs.umd.edu/~pugh/java/memoryModel/DoubleCheckTest.java} is a test case showing that it does not work 

Before java 1.5 this way was not working but from 1.5 using the keyword `volatile` allows it to work.

```java
public class Something {
  private volatile Something instance;
  
  private Something() {}
  
  public synchronized static Something getInstance() {
    if (instance == null) {
      synchronized (this) {
        if (instance == null) {
          instance = new Something();
        }
      }
    }
    return instance;
  }
}
```


## Using an enum
```java
public enum Something {
  INSTANCE;

  public static Something getInstance() {
      return INSTANCE;
  }
}
```
Despite looking like it is not lazy initialisation, it is. As the class will be initialised only the first time `INSTANCE` is called.


## Using an holder
```java
public class Something {
  private Something() {}

  private static class LazyHolder {
    static final Something INSTANCE = new Something();
  }

  public static Something getInstance() {
    return LazyHolder.INSTANCE;
  }
}
```
