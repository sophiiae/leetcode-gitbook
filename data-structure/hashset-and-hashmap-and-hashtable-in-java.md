# HashSet & HashMap & HashTable in Java

## HashSet and HashMap

**1\) Implementation:** HashMap implements Map interface and HashSet implements Set interface.

**2\) Duplicates:** HashSet does’t allow duplicate values. HashMap store key, value pairs and it does not allow duplicate keys. If key is duplicate then old key is replaced with new value.

**3\) Number of objects during storing objects :** HashMap requires two objects put\(K key, V Value\) to add an element to HashMap object, while HashSet requires only one object add\(Object o\) .

**4\) Dummy value :** In HashMap no concept of dummy value,  
HashSet internally uses HashMap to add elements. In HashSet, the argument passed in **add\(Object\)** method serves as key K. Java internally associates dummy value for each value passed in add\(Object\) method.

**5\) Storing or Adding mechanism :** HashMap internally uses hashing to store or add objects, HashSet internally uses HashMap object to store or add the objects.

**6\) Faster:**HashSet is slower then HashMap,

**7\) Insertion** HashMap use put\(\) method for storing data, While in HashSet use add\(\) method for add or storing data.

**8\) Example:** HashSet is a set, e.g. {1, 2, 3, 4, 5, 6, 7},

HashMap is a key -&gt; value pair\(key to value\) map, e.g. {a -&gt; 1, b -&gt; 2, c -&gt; 2, d -&gt; 1}

## HashMap and HashTable

There are several differences between [`HashMap`](http://java.sun.com/javase/7/docs/api/java/util/HashMap.html) and [`Hashtable`](http://java.sun.com/javase/7/docs/api/java/util/Hashtable.html) in Java:

1. `Hashtable` is [synchronized](https://stackoverflow.com/questions/1085709/what-does-synchronized-mean), whereas `HashMap` is not. This makes `HashMap` better for non-threaded applications, as unsynchronized Objects typically perform better than synchronized ones.
2. `Hashtable` does not allow `null` keys or values. `HashMap` allows one `null` key and any number of `null` values.
3. One of HashMap's subclasses is [`LinkedHashMap`](http://java.sun.com/javase/7/docs/api/java/util/LinkedHashMap.html), so in the event that you'd want predictable iteration order \(which is insertion order by default\), you could easily swap out the `HashMap` for a `LinkedHashMap`. This wouldn't be as easy if you were using `Hashtable`.



