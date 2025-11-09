# System_Design

Design a simple in memory cache system

Functional requirements

1. Store a key-value pairs in the memory
2. retrieve value for a key if it exists
3. automatically evict items when capacity is full (LRU policy)
4. Update the value of key if it already exists
5. Display current cache state.

Non-Functional requirements

1. In-memory only
2. thread-safe concurrent access
3. O(1) complexity
4. Light-weight & easily extendable


Algo Choice

We will use the lru eviction policy-based on ordered dict from pythons collection module

  this ensures O(1) insertion , deletion and access while preserving the order of the usage

Concurrency & Datamodel

1. The cache is thread safe suing threading lock

Data  Model-

  Key : Unique string/int identifier
  value: any python object
  capacity:fixed integer limit

lock ensures concurrent get() and put()


UML Diagram

In memory cache class

-capacity:: int
-cache: ordered dict
-lock: threading.lock

+get(key)-> value
+put(key,value)
+display()
