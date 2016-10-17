# Longest Increasing Subsequence

## Problem
---
Given a sequence, your mission is that find a longest increasing subsequence in given sequence. A subsequence doesn't need to be continuos. For example, a sequence {3, 2, 6, 4, 5, 1}, the longest increasing subsequence will be __{3, 4, 5}__ or __{2, 4, 5}__ and the length is __3__.

## Thought
---

## Algorithm
---
#### Recursion Form


## Solution
---
A = {3, 2, 6, 4, 5, 1}

##### step 1: Initialize

| arr | 3 | 2 | 6 | 4 | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 1 | 1 | 1 | 1 |


##### step 2:

Now index _i = 2_, _j = 1_.
```
arr[1] = 3 > arr[2] = 2
```
We don't anything.

| arr | <font color="red">3</font> | <font color="blue">2</font> | 6 | 4 | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 1 | 1 | 1 | 1 |


##### step 3:

Next round _i = 3_, _j = 1_.
```
arr[1] = 3 < arr[3] = 6
```
So __lcs[3] = max(lcs[3] ,lcs[1] + 1)__.

| arr | <font color="red">3</font> | 2 | <font color="blue">6</font> | 4 | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | <font color="blue">2</font> | 1 | 1 | 1 |

#### ...4...

##### step 5:

Next round _i = 4_, _j = 1_.
```
arr[1] = 3 < arr[4] = 4
```
So __lcs[4] = max(lcs[4] ,lcs[1] + 1)__.

| arr | <font color="red">3</font> | 2 | 6 | <font color="blue">4</font> | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 2 | <font color="blue">2</font> | 1 | 1 |

##### step 6:

Next round _i = 4_, _j = 2_.
```
arr[2] = 2 < arr[4] = 4
```
So __lcs[4] = max(lcs[4] ,lcs[2] + 1)__, we don't change anything.

| arr | 3 | <font color="red">2</font> | 6 | <font color="blue">4</font> | 5 | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 2 | <font color="blue">2</font> | 1 | 1 |

##### ...7...8...9...10...

##### step 11:

Next round _i = 5_, _j = 4_.
```
arr[4] = 4 < arr[5] = 5
```
So __lcs[5] = max(lcs[5] ,lcs[4] + 1)__, we add one plus.

| arr | 3 | 2 | 6 | <font color="red">4</font> | <font color="blue">5</font> | 1 |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 2 | 2 | <font color="blue">3</font> | 1 |

##### ...12...13...14...15...

##### step final:

Next round _i = 6_, _j = 5_.
```
arr[5] = 5 > arr[6] = 1
```

| arr | 3 | 2 | 6 | 4 | <font color="red">5</font> | <font color="blue">1</font> |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| lcs | 1 | 1 | 2 | 2 | 3 | <font color="blue">1</font> |


We got the longest increasing subsequence length is __3__.

## Complexity
---
Time Complexity: __Big-O(n)__
<br>
Space Complexity: __Big-O(n<sup>2</sup>)__

## Source Code
---
