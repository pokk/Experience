# Longest Common Substring

## Problem
---
Given two strings <font color="gray">__'ACBAD'__</font> and <font color="gray">__'ABAC'__</font> for the input. Your mission is finding a longest common string from this two strings.<br>
As this input example, you can find a longest common string is <font color="gray">__'ABA'__</font> from them so the answer will be 3.

## Thought
---
We have a thinking is using __*brute-force attack*__ to solve it.
<br>
1. Show all of the X's substring.
2. Show all of the Y's substring.
3. Pick up the same all substring and chose the longest substring from them.

We can try to calculate the time complexity of them.
<br>
_Step 1_ Big-O(2^len(X)).
<br>
_Step 2_ Big-O(2^len(Y)).
<br>
_Step 3_ We don't need to calculate it because it will be exponential time.
<br>
This is totally not a good way to solve it.

<br>
The other way, we try to use __*dynamic programming*__.
<br>
We can start considering a optimal substructure. Here are two strings X:_GOOD_, Y:_GOTO_, and Z is LCS(X, Y). We can find the same word from the tail of both of strings, we can know there are three conditions will be happened.
1. if __Xt = Yt__ then __Zt <- the tail of the same word__.
2. if __Xt != Yt__ then __Zt <- the__.

## Algorithm
---
#### Recursion Form

You can see the form as below:
<br>
![LCS formula](../../img/LCS formula.png)

## Solution
---
String A: ABCDF
<br>
String B: ACDCFD


##### step 1: Initialize

|   |   | A | B | C | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| A | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |


##### step 2:

|   |   | <font color="red">A</font> | B | C | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| <font color="red">A</font> | 0 | <font color="red">1 ↘</font> | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### step 3:

|   |   | A | <font color="red">B</font> | C | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| <font color="red">A</font> | 0 | 1 | <font color="green">1 →</font> | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### step 4:

|   |   | A | B | <font color="red">C</font> | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| <font color="red">A</font> | 0 | 1 ↘ | 1 → | <font color="green">1 →</font> | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### ...5...6...

##### step 7:

|   |   | <font color="red">A</font> | B | C | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| A | 0 | 1 ↘ | 1 → | 1 → | 1 → | 1 → |
| <font color="red">C</font> | 0 | <font color="green">1 ↓</font> | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### ...8...

##### step 9:

|   |   | A | B | <font color="red">C</font> | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| A | 0 | 1 ↘ | 1 → | 1 → | 1 → | 1 → |
| <font color="red">C</font> | 0 | 1 ↓ | 1 ↓ | <font color="red">2 ↘</font> | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### step 10:

|   |   | A | B | <font color="red">C</font> | D | F |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| A | 0 | 1 ↘ | 1 → | 1 → | 1 → | 1 → |
| <font color="red">C</font> | 0 | 1 ↓ | 1 ↓ | 2 ↘ | <font color="green">2 →</font> | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |
| C | 0 | 0 | 0 | 0 | 0 | 0 |
| F | 0 | 0 | 0 | 0 | 0 | 0 |
| D | 0 | 0 | 0 | 0 | 0 | 0 |

##### ...11...12...13...14...15...16...17.......

##### final:

|   |   | A | B | C | D | <font color="red">F</font> |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| A | 0 | 1 ↘ | 1 → | 1 → | 1 → | 1 → |
| C | 0 | 1 ↓ | 1 → | 2 ↘ | 2 → | 2 → |
| D | 0 | 1 ↓ | 1 → | 2 → | 3 ↘ | 3 → |
| C | 0 | 1 ↓ | 1 → | 2 ↘ | 3 ↓ | 3 → |
| F | 0 | 1 ↓ | 1 → | 2 → | 3 ↓ | 4 ↘ |
| <font color="red">D</font> | 0 | 1 ↓ | 1 → | 2 ↓ | 3 ↘ | <font color="pink">4 ↓</font> |

So, the max length result: __4__

#### Backtracking

We can use backtracking to find the string we recorded.

|   |   | <font color="blue">A</font> | B | <font color="blue">C</font> | <font color="blue">D</font> | <font color="blue">F</font> |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
|   | 0 | 0 | 0 | 0 | 0 | 0 |
| <font color="blue">A</font> | 0 | <font color="blue">1 ↘</font> | <font color="blue">1 →</font> | 1 → | 1 → | 1 → |
| <font color="blue">C</font> | 0 | 1 ↓ | 1 → | <font color="blue">2 ↘</font> | 2 → | 2 → |
| <font color="blue">D</font> | 0 | 1 ↓ | 1 → | 2 → | <font color="blue">3 ↘</font> | 3 → |
| C | 0 | 1 ↓ | 1 → | 2 ↘ | <font color="blue">3 ↓</font> | 3 → |
| <font color="blue">F</font> | 0 | 1 ↓ | 1 → | 2 → | 3 ↓ | <font color="blue">4 ↘</font> |
| D | 0 | 1 ↓ | 1 → | 2 ↓ | 3 ↘ | <font color="blue">4 ↓</font> |

the max string result: __ACDF__

## Complexity
---
Time Complexity: __Big-O(mn)__
<br>
Space Complexity: __Big-O(mn)__

## Source Code
---
URL
