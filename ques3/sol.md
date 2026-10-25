# `zer0OoO0` 
<div align="center">

<img src="https://capsule-render.vercel.app/api?type=venom&height=120&color=0:09090B,50:27272A,100:4C1D95&text=DAY%20003&fontColor=E4E4E7&fontSize=46&fontAlignY=50&animation=fadeIn&stroke=6D28D9&strokeWidth=1" width="100%" />

![Language](https://img.shields.io/badge/LANGUAGE-PYTHON_3-18181B?style=flat-square&labelColor=09090B&color=6D28D9)
![Time](https://img.shields.io/badge/TIME-O(n)-18181B?style=flat-square&labelColor=09090B&color=7C3AED)

</div>

## ` solution `

```python
def analyze_intervals(A, B):
    #  merge two sorted arrays.
    i = j = 0
    intervals = []

    while i < len(A) and j < len(B):
        if A[i][0] <= B[j][0]:
            intervals.append(A[i])
            i += 1
        else:
            intervals.append(B[j])
            j += 1

    intervals.extend(A[i:])
    intervals.extend(B[j:])

    if not intervals:
        return {
            "merged": [],
            "longest": None,
            "duration": 0
        }

    # compact overlapping intervals in place.
    slow = 0

    for fast in range(1, len(intervals)):
        current = intervals[fast]
        last = intervals[slow]

        if current[0] <= last[1]:
            last[1] = max(last[1], current[1])
        else:
            slow += 1
            intervals[slow] = current

    merged = intervals[:slow + 1]

    # longest merged interval.
    longest = merged[0]
    max_duration = longest[1] - longest[0]

    for interval in merged[1:]:
        duration = interval[1] - interval[0]

        if duration > max_duration:
            longest = interval
            max_duration = duration

    return {
        "merged": merged,
        "longest": longest,
        "duration": max_duration
    }
```

