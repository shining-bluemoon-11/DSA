# `zer0OoO0` // SOLUTION ARCHIVE

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=130&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20002&fontColor=E4E4E7&fontSize=48&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=3000&pause=1000&color=A78BFA&center=true&vCenter=true&width=460&lines=QUEUE+%2B+STACK+%2B+TREE;BFS+%2F%2F+HASHING+%2F%2F+PATH+RECONSTRUCTION;ANOMALY+DETECTED+%3A%3A+SOLUTION+UNLOCKED" />

<br/>

![Difficulty](https://img.shields.io/badge/DIFFICULTY-MEDIUM-18181B?style=flat-square&labelColor=09090B&color=7C3AED)
![Language](https://img.shields.io/badge/LANGUAGE-PYTHON_3-18181B?style=flat-square&labelColor=09090B&color=6D28D9)

</div>

### Algorithm

1. If the root is `None`, return `[]`.
2. Initialize a queue with the root.
3. Maintain a set named `seen` for previously visited values.
4. Maintain a dictionary named `parent` mapping each node object to its parent.
5. Process nodes in BFS order, adding children from left to right.
6. If a node's value already exists in `seen`, that node is the first repeated occurrence.
7. Follow its parent references to the root, pushing values onto a stack.
8. Pop the stack to produce the root-to-node path.
9. If traversal finishes without a duplicate, return `[]`.



## `// PYTHON IMPLEMENTATION`

```python
from collections import deque


class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right


def detect_anomaly(root):
    if root is None:
        return []

    queue = deque([root])
    seen = {root.val}

    parent = {root: None}

    while queue:
        node = queue.popleft()

        for child in (node.left, node.right):
            if child is None:
                continue

            parent[child] = node

            if child.val in seen:
   
                stack = []
                current = child

                while current is not None:
                    stack.append(current.val)
                    current = parent[current]

                return stack[::-1]

            seen.add(child.val)
            queue.append(child)

    return []
```
