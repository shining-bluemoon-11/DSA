# `zer0OoO0` 

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=130&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20001&fontColor=E4E4E7&fontSize=48&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=3000&pause=1000&color=A78BFA&center=true&vCenter=true&width=460&lines=STACK+%2B+QUEUE+%2B+BINARY+TREE;DETECTING+STRUCTURAL+ANOMALIES;ONE+COMMIT+CLOSER+TO+THE+UNKNOWN" />

<br/>

![Challenge](https://img.shields.io/badge/CHALLENGE-DAY--001-18181B?style=flat-square&labelColor=09090B&color=6D28D9)
![Difficulty](https://img.shields.io/badge/DIFFICULTY-MEDIUM-18181B?style=flat-square&labelColor=09090B&color=7C3AED)

</div>

---

## `01 //PROBLEM`

**Problem: Tree Traversal Anomaly Detector**

A binary tree is transmitting a sequence of node values. Some values may appear more than once, indicating a potential anomaly.

Your mission is to traverse the tree level by level, identify the **first repeated value**, and return the path from the root to the node where that value repeats.

Your solution must combine three core data structures:

- **Queue** — perform level-order traversal (BFS).
- **Hash set / dictionary** — track previously encountered values.
- **Stack** — reconstruct the path from the root to the repeated node.

If no repeated value exists, return an empty list.

## `02 // INPUT SPECIFICATION`

You are given the root node of a binary tree.

Each node contains:
- An integer value.
- A reference to its left child.
- A reference to its right child.

### Constraints

- \(0 \le n \le 10^5\)
- \(-10^9 \le node.val \le 10^9\)
- The tree may be empty.
- Node values are not necessarily unique.

## `03 // EXAMPLE EXECUTION`

### Example 1 — Anomaly detected

```text
          1
         / \
        2   3
       / \   \
      4   5   2
```

**Input:** `root = [1, 2, 3, 4, 5, null, 2]`

**Level-order traversal:**

```text
1 → 2 → 3 → 4 → 5 → 2
```

**Output:**

```python
[1, 3, 2]
```

**Explanation:**

The value `2` first appears at the left child of the root. It appears again as the right child of node `3`.

The path to the repeated node is:

```text
1 → 3 → 2
```

The traversal must stop at the first repeated value encountered in level order.

### Example 2 — No anomaly

```text
        10
       /  \
      20   30
```

**Input:** `root = [10, 20, 30]`

**Output:**

```python
[]
```

**Explanation:** All node values are unique.

### Example 3 — Repeated siblings

```text
        1
       / \
      2   2
```

**Input:** `root = [1, 2, 2]`

**Output:**

```python
[1, 2]
```

**Explanation:** The right child is the first repeated occurrence of value `2` in level-order traversal. The output gives its root-to-node path.

### Example 4 — Empty tree

**Input:** `root = []`

**Output:**

```python
[]
```

**Explanation:** An empty tree contains no repeated values.

## `04 // REQUIRED ALGORITHM`

Your implementation must:

1. Initialize a queue with the root node.
2. Process nodes in level-order traversal.
3. Maintain a set or dictionary of previously encountered values.
4. Store parent references for path reconstruction.
5. When a repeated value is encountered, identify that specific node.
6. Trace the node's parent chain to the root using a stack.
7. Reverse the collected path by popping the stack.
8. Return the resulting root-to-node path.
9. Return [] if no repeated value is found.

Tie-breaking rule: Process nodes from left to right within each level. The first duplicate encountered determines the answer


<div align="center">

<img src="https://img.shields.io/badge/The system is learning. The destination remains unknown.-18181B?style=flat-square&labelColor=09090B&color=6D28D9" />


</div>