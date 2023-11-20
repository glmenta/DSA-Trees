### Trees have a hierarchial data structure

```
Root -> Child -> Leaf

Ex:
Facebook comments -> tree DS;
```

### Binary Trees
```
=> Each node can only have 0, 1 or 2 nodes
=> Each node represents a certain state

Creating a Binary Tree:

function BinaryTreeNode(val) {
  this.val = val;
  this.left = null;
  this.right = null;
}

Perfect BT => all the nodes are filled in (0 or 2) and bottom layer is filled; Every layer's # of nodes is doubled
Full BT => A node has either 0 or 2 children but never 1 child but the bottom layer is not all filled

BST lookup, insert and delete O(logN)
```

### O(logN)
```
 1 => 2 => 4 => 8

h => levels

# of nodes = 2 ^ h - 1
log nodes = steps in tree

log n => means that based on height, max num of decisions required to find target node
"Divide and Conquer" => Idea of log N is similar to looking through a phone book; 
```

### Binary Search Tree
```
BST lookup, insert and delete O(logN)

Lookup => faster than iterating

=> Preserve relationships
=> All child nodes to the right are larger in value
=> left are smaller in value
=> only maximum two child nodes
```

### Balanced vs Unbalanced and BST Pros/Cons
```
=> Unbalanced basically looks like a Linked List;
=> Inefficient since our time complexity goes from being O(logN) to O(n)

Pros:
=> Better than O(n), Ordered and Flexible Size

Cons:
=> No O(1) operations
```
### BST Implementation
```
class Node {
  constructor(val) {
    this.left = null;
    this.right = null;
    this.length = val;
  }
}

class BST {
  constructor() {
    this.root = null;
  }

  insert(val) {
    const newNode = new Node (val);
    if (!this.root) {
      this.root = newNode;
    } else {
      let currNode = this.root;
      while(true) {
        if (val < currNode.val) {
        //go Left
          if (!currNode.left) {
            currNode.left = newNode;
            return this;
          }
          currNode = currNode.left
        } else {
        //go Right
        if(!currNode.right) {
          currNode.right = newNode;
          return this;
        }
        currNode = currNode.right;
  }

  lookup(val) {
    if (!this.root) return false;
    let curr = this.root;
    while(curr) {
      if (curr.val > val) {
        //go left
        curr = curr.left

      } else if (curr.val < val){
        //go right
        curr = curr.right
      } else  if (curr.val === val) {
        return curr
      }
    return false;
    }
 
  }
}
```

### Priority Queues
```
Memory Heap !== Heap Data Structure

Priority Queue => each ele have their own specific priority;
=> like a club, VIPS can go in first

Binary Heaps
Pros: Better than O(n), priority, flexible size, fast insert
Con: Slow lookup
```

```

