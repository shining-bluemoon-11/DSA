# `zer0OoO0` \
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=120&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20004&fontColor=E4E4E7&fontSize=46&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

![Language](https://img.shields.io/badge/LANGUAGE-PYTHON_3-18181B?style=flat-square&labelColor=09090B&color=6D28D9)
![Algorithm](https://img.shields.io/badge/ALGORITHM-GREEDY%20%2B%20HEAP-18181B?style=flat-square&labelColor=09090B&color=7C3AED)

</div>

---

## ` PYTHON implement`

```python
import heapq


def schedule_tasks(tasks, k):
    tasks = sorted(tasks, key=lambda x: (x[1], x[0]))

    if k == 0:
        return {
            "count": 0,
            "selected": [],
            "skipped": sorted(tasks, key=lambda x: (x[0], x[1]))
        }

    available = []

    selected = []
    skipped = []

    for start, end in tasks:
        if available and available[0] <= start:
            # Reuse first free
            heapq.heapreplace(available, end)

            selected.append([start, end])

        elif len(available) < k:
            # allocte new resource
            heapq.heappush(available, end)

            selected.append([start, end])

        else:
            #  all resorces occupied.
            skipped.append([start, end])

    selected.sort(key=lambda x: (x[0], x[1]))
    skipped.sort(key=lambda x: (x[0], x[1]))

    return {
        "count": len(selected),
        "selected": selected,
        "skipped": skipped
    }
```



## ` topics`

- Sorting intervals by end time
- Greedy scheduling
- Min-heap operations
- Resource availability tracking
- Overlap handling
- Half-open interval semantics
- Complexity analysis



<div align="center">

*Think strategically. Schedule greedily. Optimize relentlessly.*

</div>
