# `zer0OoO0` 
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=130&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20004&fontColor=E4E4E7&fontSize=48&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&size=13&duration=3000&pause=1000&color=A78BFA&center=true&vCenter=true&width=470&lines=INTERVALS+%2B+GREEDY+%2B+MIN+HEAP;RESOURCE+ALLOCATION+PROTOCOL;MAXIMUM+TASKS+%2F%2F+MINIMUM+CONFLICTS" />

<br/>

![Difficulty](https://img.shields.io/badge/DIFFICULTY-MEDIUM--HARD-18181B?style=flat-square&labelColor=09090B&color=7C3AED)
![Topics](https://img.shields.io/badge/TOPICS-HEAP%20%7C%20INTERVALS-18181B?style=flat-square&labelColor=09090B&color=6D28D9)

</div>

---

## `01 // `

### Resource-Constrained Interval Scheduler

A computing system receives a list of tasks. Each task occupies one resource for a fixed interval `[start, end]`.

The system has exactly `k` identical resources. A resource can run at most one task at a time, but different resources can execute tasks simultaneously.

Your objective is to **schedule the maximum possible number of tasks** without allowing more than `k` tasks to run simultaneously.

You must use a greedy algorithm and a min-heap to track resource availability.

## `02 // Function`

```python
def schedule_tasks(tasks, k):
    pass
```

Each task is represented as:

```python
[start, end]
```

Return a dictionary containing:

- `count`: the maximum number of scheduled tasks.
- `selected`: the selected intervals, in chronological start-time order.
- `skipped`: the intervals that were not selected, in chronological start-time order.

If `k == 0`, no tasks can be scheduled.

## `03 // EXAMPLE `

### Example 1

```python
tasks = [
    [1, 4],
    [2, 3],
    [3, 5],
    [4, 6],
    [6, 8]
]
k = 2
```

**One valid optimal output:**

```python
{
    "count": 4,
    "selected": [[1, 4], [2, 3], [4, 6], [6, 8]],
    "skipped": [[3, 5]]
}
```

The two resources can run tasks concurrently, but no resource can run overlapping tasks.

Intervals are treated as half-open: `[start, end)`. A task ending at time `4` frees its resource for a task starting at time `4`.

### Example 2 — One resource

```python
tasks = [[1, 5], [2, 3], [3, 4], [4, 6]]
k = 1
```

**Output:**

```python
{
    "count": 3,
    "selected": [[2, 3], [3, 4], [4, 6]],
    "skipped": [[1, 5]]
}
```

Selecting the shorter compatible tasks allows more work to finish.

### Example 3 — No resources

```python
tasks = [[1, 3], [2, 4]]
k = 0
```

**Output:**

```python
{
    "count": 0,
    "selected": [],
    "skipped": [[1, 3], [2, 4]]
}
```

## `04 // REQUIRED RULES`

1. Sort tasks by increasing end time; use start time as a secondary sorting key.
2. Use a min-heap to track when resources become available.
3. If the earliest available resource is free by the task's start time, assign the task to it.
4. Otherwise, skip the task.
5. Return selected and skipped intervals in chronological start-time order.
6. Each task must be assigned to at most one resource.
7. Use half-open intervals: a task ending at `t` does not overlap one starting at `t`.

If multiple optimal schedules exist, any maximum-cardinality schedule is acceptable.

## `05 // CONSTRAINTS`

- \(0 \le n \le 2 \times 10^5\)
- \(0 \le k \le 10^5\)
- \(0 \le start < end \le 10^9\)
- Tasks may overlap arbitrarily.
- All resources are identical.

## `06 // COMPLEXITY TARGET`

- Time: \(O(n \log n + n \log k)\), with heap operations bounded by the number of resources.
- Space: \(O(n + k)\), including the selected and skipped results.



<div align="center">

*Optimize the schedule. Minimize idle resources. Maximize completed tasks.*

</div>
