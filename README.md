# LeetCode 100 — Same Tree

## Problem
Given the roots of two binary trees `p` and `q`, write a function to check if they are the same or not.

Two binary trees are considered the same if:

- They are structurally identical
- The nodes have the same values

---

## Example

Input:
```text
p = [1,2,3]
q = [1,2,3]
```

Output:
```text
true
```

---

## Approach
Use DFS recursion:

- If both nodes are `null` → return `true`
- If one node is `null` and the other is not → return `false`
- If node values are different → return `false`
- Recursively compare:
  - left subtrees
  - right subtrees

---

## Java Solution

```java
class Solution {

    public boolean isSameTree(TreeNode p, TreeNode q) 
    {
        if(p == null && q == null)
        {
            return true;
        }

        if(p == null || q == null)
        {
            return false;
        }

        if(p.val != q.val)
        {
            return false;
        }

        return isSameTree(p.left, q.left) &&
               isSameTree(p.right, q.right);
    }
}
```

---

## Time Complexity
```text
O(n)
```

Each node is visited once.

---

## Space Complexity
```text
O(h)
```

- `h` = height of tree
- Recursive stack space

---

## Key Concepts
- Binary Tree
- DFS
- Recursion
- Tree Traversal
