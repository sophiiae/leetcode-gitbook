# Hash Table, Map, Object, Set \(JS\)

* [Hash Table](hash-table-map-object-set-js.md#hash-table)
* [Map](hash-table-map-object-set-js.md#map)
* [Object](hash-table-map-object-set-js.md#object)
* [Set](hash-table-map-object-set-js.md#set)

## Hash Table

* A dictionary-like structure key-value pairs.
* Location in memory of each pair is determined by a `hash function`, which accept keys and return the _address_ of the pair.  
* **Hash Function**
  * Hash Code: keys -&gt; integers 
  * Compression function: integers -&gt; \[0, N\], e.g. y mod N
* Collision Handling 
  * Separate Chaining: each cell point to a linked list of entries
  * Linear Probing: put in next available cell
  * Double Hashing: use second hash function
* **Worst Case**: when all keys insert to the map collide **** – O\(n\)
* **Average Case**: O\(1\)
* Representation 
  * Array 
  * [Map ](hash-table-map-object-set-js.md#map)
  * [Object ](hash-table-map-object-set-js.md#object)

## Map

* a iterable collection of key-value entries, **unique keys**

```javascript
const map = new Map();
let len = map.length; //0
map.set('a',0);
map.set('b',1);
map.has('a'); // true
/* return a new iterator object contain all elements in insertion order*/
let iter = map.entries();
iter.next().value // ['a',0]
/* return a new iterator object contain the keys */
let keys = map.keys();
keys.next().value; // 'a'
/* return a new iterator object contain the values */
let vals = map.values();
vals.next().value; // 0
map.delete('a') // true, successfully remove element, ow return false
map.forEach((k,v) => v += 1);
map.get('b'); //2
map.has('c'); // false
map.clear(); // remove all pairs from the map object
```

## Object

* Pairs of names\(strings\) and values\(any value\)

```javascript
const obj = new Object();
const obj2 = {a: 1, b: 2};
/* copy the value of all enumerate properties to target object */
Object.assign(obj, obj2); // {a: 1, b: 2}; return obj
/* creates a new object, using an existing object as the prototype */
const obj3 = Object.create(obj);

const arr = Object.entries(obj); //[[a,1],[b,2]]
const keys = Object.keys(obj); //['a','b']
const vals = Object.values(obj); //[1,2]

Object.freeze(obj); //freeze an object, cannot be changed after. 
const obj4 = Object.fromEntries([['k','c'],['l',5']]); // {k:'c', l:5}
Object.is(obj, obj1); //false
Object.is('bar','bar'); //true
Object.isExtensible(obj); //true, determines if an object is extensible
Object.isFronzen(obj); //true, determines if an object is frozen
```

## Set

* Store **unique** values of any type

```javascript
const set1 = new Set();
set1.add(42); //[42]
set1.add(13); //[42,13]
set1.delete(42); //[13]
set1.forEach(v => {
    if (v > 20) set1.delete(v); 
    } 
set1.has(10); //false
const iter = set1.entries();
const vals = set1.values(); 
const keys = set1.keys(); //same as values() in map
```



