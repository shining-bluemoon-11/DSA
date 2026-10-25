# `zer0OoO0` 
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=130&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20003&fontColor=E4E4E7&fontSize=48&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=3000&pause=1000&color=A78BFA&center=true&vCenter=true&width=470&lines=TWO+POINTERS+%2B+MERGE+INTERVALS;SLOW+%2F%2F+FAST+%2F%2F+ARRAY+COMPACTION;COLLISION+DETECTION+PROTOCOL" />

<br/>

![Difficulty](https://img.shields.io/badge/DIFFICULTY-MEDIUM-18181B?style=flat-square&labelColor=09090B&color=6D28D9)
![Topics](https://img.shields.io/badge/TOPICS-ARRAYS%20%7C%20POINTERS-18181B?style=flat-square&labelColor=09090B&color=7C3AED)

</div>

---

## `01 `

### Interval Collision Engine

Two independent systems generate sorted time intervals representing periods of activity.

Each interval is represented as `[start, end]`. Within each system, intervals are sorted by start time and do not overlap.

Combine both systems into one timeline, merge all overlapping intervals, and identify the longest continuous period of activity.

Your solution must use:

- Two pointers to merge the two sorted interval arrays.
- A fast pointer to scan the combined array.
- A slow pointer to compact merged intervals in place.
- Interval merging to combine overlapping ranges.

## `02 // FUNCTION SIGNATURE`

```python
def analyze_intervals(A, B):
    pass
```

Return a dictionary containing:

- `merged`: all merged intervals, sorted by start time.
- `longest`: the interval with the greatest duration.
- `duration`: the duration of that interval.

If there are no intervals, return:

```python
{
    "merged": [],
    "longest": None,
    "duration": 0
}
```

If multiple merged intervals have the same maximum duration, return the earliest one.

## `03 `

### Example 1

```text
A = [[1, 3], [8, 10], [15, 18]]
B = [[2, 6], [11, 14], [17, 20]]
```

**Output:**

```python
{
    "merged": [[1, 6], [8, 10], [11, 14], [15, 20]],
    "longest": [1, 6],
    "duration": 5
}
```

**Explanation:**

- `[1, 3]` and `[2, 6]` overlap, producing `[1, 6]`.
- `[8, 10]` remains separate.
- `[11, 14]` remains separate.
- `[15, 18]` and `[17, 20]` overlap, producing `[15, 20]`.
- The first and last merged intervals both have duration `5`, so the earliest wins.

### Example 2 — Fully overlapping intervals

```text
A = [[1, 5]]
B = [[2, 3], [4, 8]]
```

**Output:**

```python
{
    "merged": [[1, 8]],
    "longest": [1, 8],
    "duration": 7
}
```

### Example 3 — No intervals

```text
A = []
B = []
```

**Output:**

```python
{
    "merged": [],
    "longest": None,
    "duration": 0
}
```

## `04 // REQUIRED RULES`

1. Both input arrays are sorted by start time.
2. Each input array contains internally non-overlapping intervals.
3. Treat intervals as closed intervals for merging: `[a, b]` and `[b, c]` merge.
4. Merge the two sorted arrays using two pointers.
5. Use fast and slow indices to merge intervals in place.
6. Return the longest merged interval, breaking ties by earliest start.
7. Duration is calculated as `end - start`.

## `05 // CONSTRAINTS`

- \(0 \le |A|, |B| \le 10^5\)
- \(0 \le start \le end \le 10^9\)
- Each input array is sorted.
- Each input array contains no overlapping intervals internally.

## `06 // COMPLEXITY TARGET`

Let \(n = |A| + |B|\).

- Time: \(O(n)\)
- Auxiliary space: \(O(n)\) for the combined array.
- Interval compaction itself: \(O(1)\) auxiliary space.



<div align="center">


*Merge the signals. Eliminate the collisions. Find the longest run.*

</div>
