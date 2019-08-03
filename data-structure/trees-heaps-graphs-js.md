# Trees, Heaps, Graphs

* [Trees ](trees-heaps-graphs-js.md#trees)
  * [Binary Tree](trees-heaps-graphs-js.md#binary-tree)
  * [Binary Search Tree](trees-heaps-graphs-js.md#binary-search-tree)
  * [AVL Trees](trees-heaps-graphs-js.md#avl-tree) 
  * [Splay Trees ](trees-heaps-graphs-js.md#splay-tree)
  * [Red Black Trees](trees-heaps-graphs-js.md#red-black-tree)
* [Heaps](trees-heaps-graphs-js.md#heaps)
  * [Max Heap ](trees-heaps-graphs-js.md#max-heap)
  * [Min Heap](trees-heaps-graphs-js.md#min-heap)
* [Graphs](trees-heaps-graphs-js.md#graphs)
  * [Depth First Search - stack](trees-heaps-graphs-js.md#depth-first-search)
  * [Breadth First Search - queue](trees-heaps-graphs-js.md#breadth-first-search)

## Trees

### **Terminology**

* **Depth** – number of ancestors \(exclude itself\)
* **Height** – maximum depth of any node
* **Traversal**
  * **Preorder**: a node is visited before its descendants
  * **Postorder**: a node is visited after its descendants

```javascript
 function Node(val, children) {
    this.val = val;
    this.children = children;
 };
```

### Binary Tree 

* Each internal node has at **most** two children
* Children of a node are an ordered pair
* **Proper Binary Tree** 
  * if each node has 0 or 2 children
* **Traversal** 
  * **Inorder**: left -&gt; root -&gt; right
  * **Preorder**: root -&gt; left -&gt; right
  * **Postorder**: left -&gt; right -&gt; root

```javascript
 function TreeNode(val) {
     this.val = val;
     this.left = this.right = null;
 }
```

### Binary Search Tree

* Left &lt; Root &lt; Right
* **Search**: cut sub-tree in half, determine which half the key would be in
* **Insertion:** expand an internal node / update value
* **Deletion**: replace with its left right-most node value, delete left right-most node
* **Performance**
  * Find, insert, remove – O\(n\) worst case \(all node in one side\)
  * Find, insert, remove – O\(log n\) best case \(balanced tree\)

### AVL Tree

* First **balanced** binary search tree 
* **Heights** of siblings can **differ** by at most **1**
* Minimize single look up time, not exceed O\(log n\)
* Useful in **multithreaded** environments

### Splay Tree

* Self-balancing BST
* 3 Types of Splay Steps 
  * Zig-Zig
  * Zig-Zag
  * Zig
* Preferred for **lots search**, less insertion and deletion \(cause rotations\)
* Minimize total lookup time.
* Easier to implement, compare to AVL tree. 

### Red Black Tree

* Self-balancing BST
  * Each node has colour either **red** or **black**
  * No two adjacent red nodes
  * Every path from a node to any its descendant Null node has same number of black nodes
* Preferred for **lots insertions and deletions**

## Heaps 

* Binary tree with **additional rules**
* **Complete binary tree** – last node of the heap is the rightmost node of depth _h_
* Build Heap: Botton up heap construction – O\(n\)
* Insertion: **upheap** – O\(log n\)
* Deletion: **downheap** – O\(log n\)

### Max Heap

* Parent node values are **greater** than their children

                               ![](https://miro.medium.com/max/551/1*XSchy2OiWWwlkPNhhoKVBg.png)  


### Min Heap / Priority Queue

* Parent node values are **less** than their children

[                                    ![MinHeap](https://camo.githubusercontent.com/16e4220b69a866f97cc20d934c4b16fe5b9147de/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f362f36392f4d696e2d686561702e706e67)](https://camo.githubusercontent.com/16e4220b69a866f97cc20d934c4b16fe5b9147de/68747470733a2f2f75706c6f61642e77696b696d656469612e6f72672f77696b6970656469612f636f6d6d6f6e732f362f36392f4d696e2d686561702e706e67)

## Graphs

![](https://miro.medium.com/max/770/1*VM84VPcCQe0gSy44l9S5yA.jpeg)

### Depth First Search 

* Traversing down through one **branch** to the **leaf**, then back to "trunk".
* Use **Stack** – O\(n\)

### Breadth First Search

* Search through a tree **one level at a time**
* Use **Queue** – O\(n\)

