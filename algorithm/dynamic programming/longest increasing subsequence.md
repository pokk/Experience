# Longest Increasing Subsequence

## Problem
---

Given a sequence, your mission is that find a longest increasing subsequence in given sequence. A subsequence doesn't need to be continuos. For example, a sequence {3, 2, 6, 4, 5, 1}, the longest increasing subsequence will be __{2, 4, 5}__ and the length is __6__.

## Thought
---

## Algorithm
---
#### Recursion Form


## Solution
---

A = {3, 2, 6, 4, 5, 1}

| 3 | 2 | 6 | 4 | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | 0 | 0 | 0 | 0 | 0 |

The current MAX = 3
<br>
index = 2, value = 2
<br>
2 < MAX => next

6 > MAX => MAX = 6


## Complexity
---

## Source Code
---
