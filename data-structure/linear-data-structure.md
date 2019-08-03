---
description: JavaScript syntax
---

# Linear Data Structure \(JS\)

* [Array](linear-data-structure.md#array)
* [Stack](linear-data-structure.md#stack)
* [Queue](linear-data-structure.md#queue)
* [Linked List](linear-data-structure.md#linked-list)
* [JavaScript Iteration Method](linear-data-structure.md#js-iteration-methods)
* [JavaScript Loop](linear-data-structure.md#javascript-loop)
* [JavaScript Function](linear-data-structure.md#javascript-function)

## Array

* Insertion / Deletion / Search – O\(n\)
* Get / Set – O\(1\)

```javascript
const arr = Array(5).fill(0); //[0,0,0,0,0]
arr.fill(1, 2, 4); // [0,0,1,1,0] fill from 2 to 4(exclude)
let len = arr.length;
arr.reverse(); // [0,1,1,0,0] reverse order
arr.sort(); // [0,0,0,1,1] sort array
arr.splice(1, 0, 3); //[0,3,0,1,1] insert 3 at position 1
arr.splice(2, 1, 2); //[0,3,2,1,1] replace 1 element at position 2
arr.concat([6,6]); //[0,3,2,1,1,6,6] merge two arrays
arr.includes(6); //true
arr.indexOf(5); //-1 not found
arr.join(); //"0,3,2,1,1,6,6", join all elements to a string, default comma
arr.join(''); //"0321166"
arr.lastIndexOf(1); //4, return -1 if not found
arr.slice(2); //[2,1,1,6,6]
arr.slice(2, 4); //[1,6] shallow copy, from 2 to 4(exclude)
arr.toString(); // "1,6"
```

## Stack 

       ![](https://miro.medium.com/max/770/1*De8zfOowwtRZg2jBTGPvhg.jpeg)![](https://miro.medium.com/max/550/1*2S145xm6QZ9juHRGRFVHtg.jpeg)Push vs Pop functions  


**Last-In First-Out\(LIFO\)** 

* Push / Pop – O\(1\)
* Access / Search – O\(n\)

```javascript
const stack = ['k'];
stack.push('a');    //insert to the end ['k','a']
stack.pop();        //remove and return last element ['k']
stack.unshift('b'); //insert to the front ['b','k']
stack.shift();      //remove and return first element ['k']
```

## Queue

![](https://miro.medium.com/max/550/1*Vs3HF926_6s7vI_OCv3rTQ.jpeg)![](https://miro.medium.com/max/550/1*wN83zdV3arHyUl5GQXxRfw.jpeg)

**First-In First-Out\(FIFO\)** 

* Enqueue: insert to the end – O\(1\)
* Dequeue: remove and return front element – O\(1\)
* Access / Search – O\(n\)

```javascript
const queue = ['k'];
queue.unshift('a');  // ['a','k'] insert to the front
queue.pop();         // ['a'] remove last
```

## Linked List

* Get / Set – O\(n\)
* Insert / Remove – O\(1\)
* **Singly Linked List**: no space overflow\(compare to array\)
  * element 
  * link to the next node 
* **Doubly Linked List**: has special header and trailer, insert/deletion may be O\(1\) depends on the location.
  * element
  * link to the previous node
  * link to the next node 

```javascript
 function ListNode(val) {
     this.val = val;
     this.next = null;
 }
```

## JS Iteration Methods 

```javascript
const arr = [1,2,3];

/* return a new Array Iterator object contain key/value pairs for each index */
let iter1 = arr.entries().next().value; // Array [0, 1]
/* return a new Array Iterator object contain keys for each index */
let iter2 = arr.keys().next().value; // 0
/* return a new Array Iterator object contain values for each index */
let iter3 = arr.values().next().value; // 1

/* test whether all elements satisfies the condition,always true if [] */
arr.every(val => val > 2); //false
/* return true if at least one elements satisfies the condition, always false if [] */
arr.some(val => val > 2); //true

/* return value of first element satisfies the condition, o.w. return undefined */
arr.find(val => val > 0); // 1
/* return index of first element satisfies the condition, -1 if not found */
arr.findIndex(val => val > 0); // 0

/* execute function for each element, in-place */
arr.forEach(val => val + 2); //[3,4,5]
/* create a new array with result of calling function for each element */
const arr2 = arr.map(val => val * 2); //[6,8,10]
/* return new array with all elements pass the test. */
const fil = arr.filter(val => val > 1); //[2,3]
/* execute a reducer function on each element, single output value */
arr2.reduce((accumulator, cur) => accumulator + cur)); // 24, init val = first element
arr2.reduce((accumulator, cur) => accumulator + cur), 6); // 30, init val = 6
```

## JavaScript Loop

**for...in statement**

```javascript
let arr = [3, 5, 7], sum = 0;
// iterates over all enumerable properties of an object
for (let i in arr) {
    sum += arr[i] //i = 0, 1, 2
}
```

**for...of statement**

```javascript
let arr = [3, 5, 7], sum = 0;
// loop iterates over iterable objects
for (let i of arr) { 
    sum += i; //i = 3, 5, 7
}
```

**for statement** 

```javascript
for(let i = 0; i < arr.length; i++) {}
```

**do...while statement**

```javascript
let i = 0;
do {
    i++;
}while(i < 5);
```

**while statement**

```javascript
let x = 0;
while (x < 10) {
    x++;
}
```

**labeled statement** 

```javascript
mark: x += 2; 
break;  //like in switch loop
```

## JavaScript Function

```javascript
const nums = [3,4,2,1,6];
/* call a function this a given this value and an array argument */
let max = Math.max.apply(null,numbers); //6
/* call a function this a given this value and an argument list */
let min = Math.min.call(null,4,3,2); //2
```

