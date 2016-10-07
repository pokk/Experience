# Matrix Chain Multiplication

## Problem
---

## Thought
---

## Algorithm
---
#### Recursion Form
![Matrix Chain Multiplication](../../img/MCM formula.png)

## Solution
---
Here is a matrix __A1 x A2 x A3 x A4 x A5__.
<br>
A1: 4x3
<br>
A2: 3x2
<br>
A3: 2x5
<br>
A4: 5x4
<br>
A5: 4x2
<br>

step 1: Initialize

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 1 | 0 | 0 | 0 | 0 | 0 | 0 |
| 2 | 0 | 0 | 0 | 0 | 0 | 0 |
| 3 | 0 | 0 | 0 | 0 | 0 | 0 |
| 4 | 0 | 0 | 0 | 0 | 0 | 0 |
| 5 | 0 | 0 | 0 | 0 | 0 | 0 |


First, we fill up all __*i = j*__.
<br>
The matrix will be as below:

step 2:

All of the __k = 1__ case.

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | <font color="red">0</font> | 0 | 0 | 0 | 0 |
| 2 | <font color="gray">0</font> | 0 | <font color="red">0</font> | 0 | 0 | 0 |
| 3 | <font color="gray">0</font> | 0 | 0 | <font color="red">0</font> | 0 | 0 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | <font color="red">0</font> | 0 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | <font color="red">0</font> |

step 3:

Current __k = 2__.
<br>
We gonna find __m[1, 2]__: A1 x A2

```
k = 1 -> (A1 x A2) = 4 x 3 x 2 = 24
```

Here is only a case so minimum is __24__, we filled the m[1, 2] = 24.

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | 0 | <font color="red">24</font> | 0 | 0 | 0 |
| 2 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |
| 3 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |

step 4:

Current __k = 2__.
<br>
We gonna find __m[2, 3]__: A2 x A3

```
k = 1 -> (A2 x A3) = 3 x 2 x 5 = 30
```

Here is only a case so minimum is __30__, too. We filled the m[1, 2] = 30.

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | 0 | 24 | 0 | 0 | 0 |
| 2 | <font color="gray">0</font> | 0 | 0 | <font color="red">30</font> | 0 | 0 |
| 3 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |

...5...6...7...

step 8:

Current __k = 3__.
<br>
We gonna find __m[1, 3]__: A1 x A2 x A3

```
k = 1 -> (A1 x (A2 x A3)) = 0 + m[2, 3] + (4 x 3 x 5) = 90
k = 2 -> ((A1 x A2) x A3) = m[1, 2] + 0 + (4 x 2 x 5) = 64
```

There are two cases, we picked up the minimum case to fill in m[1, 3].
<br>
m[1, 3] will be __64__.

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | 0 | 24 | <font color="red">64</font> | 0 | 0 |
| 2 | <font color="gray">0</font> | 0 | 0 | 30 | 0 | 0 |
| 3 | <font color="gray">0</font> | 0 | 0 | 0 | 40 | 0 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 40 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |

...9...10...11...

step 12:

Current __k = 4__.
<br>
We gonna find __m[2, 5]__: A2 x A3 x A4 x A5

```
k = 1 -> (A2 x (A3 x A4 x A5)) = 0 + m[3, 5] + (3 x 2 x 2) = 68
k = 2 -> ((A2 x A3) x (A4 x A5)) = m[2, 3] + m[4, 5] + (3 x 5 x 2) = 100
k = 3 -> ((A2 x A3 x A4) x A5) = m[2, 4] + 0 + (3 x 4 x 2) = 88
```

There are three cases, we picked up the minimum case to fill in m[2, 5].
<br>
m[2, 5] will be __68__.

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | 0 | 24 | 64 | 96 | 0 |
| 2 | <font color="gray">0</font> | 0 | 0 | 30 | 64 | <font color="red">68</font> |
| 3 | <font color="gray">0</font> | 0 | 0 | 0 | 40 | 56 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 40 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |

step final:

|   | 0 | 1 | 2 | 3 | 4 | 5 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> | <font color="gray">0</font> |
| 1 | <font color="gray">0</font> | 0 | 24 | 64 | 96 | <font color="red">92</font> |
| 2 | <font color="gray">0</font> | 0 | 0 | 30 | 64 | 68 |
| 3 | <font color="gray">0</font> | 0 | 0 | 0 | 40 | 56 |
| 4 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 40 |
| 5 | <font color="gray">0</font> | 0 | 0 | 0 | 0 | 0 |

So, the max length result: __92__

## Complexity
---
Time Complexity: __Big-O(n^3)__
<br>
Space Complexity: __Big-O(n^2)__

## Source Code
---
