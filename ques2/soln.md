# `zer0OoO0`

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=130&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20002&fontColor=E4E4E7&fontSize=48&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=3000&pause=1000&color=A78BFA&center=true&vCenter=true&width=460&lines=BFS+%2B+HASHING+%2B+STACK;OPTIMIZED+TREE+ANALYSIS;SOLUTION+UNLOCKED" />

<br/>

![Language](https://img.shields.io/badge/LANGUAGE-PYTHON_3-18181B?style=flat-square&labelColor=09090B&color=6D28D9)
![Complexity](https://img.shields.io/badge/TIME-O(n)_EXPECTED-18181B?style=flat-square&labelColor=09090B&color=7C3AED)
![Status](https://img.shields.io/badge/STATUS-SOLVED-A78BFA?style=flat-square&labelColor=09090B&color=27272A)

</div>

---

## `01 // OPTIMIZED soln`

```python
from collections import deque


class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val
        self.left = left
        self.right = right


def analyze_tree(root):
    if root is None:
        return None

    queue = deque([root])
    seen = {root.val}

    parent = {root: None}
    depth = {root: 0}

    while queue:
        node = queue.popleft()

        for child in (node.left, node.right):
            if child is None:
                continue

            parent[child] = node
            depth[child] = depth[node] + 1

            if child.val in seen:
                stack = []
                current = child

                while current is not None:
                    stack.append(current.val)
                    current = parent[current]

                path = stack[::-1]

                return {
                    "duplicate": child.val,
                    "depth": depth[child],
                    "path": path,
                    "path_sum": sum(path)
                }

            seen.add(child.val)
            queue.append(child)

    return None
```


## `topics`

- Binary tree traversal
- BFS and queue operations
- Hash-based duplicate detection
- Parent-pointer tracking
- Stack-based path reconstruction
- Depth calculation
- Path aggregation
- Complexity analysis


