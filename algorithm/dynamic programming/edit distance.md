# Edit Distance

## Problem

---

Given two strings **str1** and **str2** and below operations that can performed on str1. Find minimum number
of edits (operations) required to convert **str1** into **str2**.

## Thought

---

## Algorithm

---

#### Recursion Form


## Solution

---

init

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| z | <font color="gray">2</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


same

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> | <font color="red">0</font>  |              0              |              0              |              0              |              0              |              0              |
| z | <font color="gray">2</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


remove

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              | <font color="red">1</font>  |              0              |              0              |              0              |              0              |
| z | <font color="gray">2</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


remove

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              |              1              | <font color="red">2</font>  |              0              |              0              |              0              |
| z | <font color="gray">2</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |

......


insert

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              |              1              |              2              |              3              |              4              |              5              |
| z | <font color="gray">2</font> | <font color="red">1</font>  |              0              |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


replace

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              |              1              |              2              |              3              |              4              |              5              |
| z | <font color="gray">2</font> |              1              | <font color="red">1</font>  |              0              |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


replace or insert

|   |                             |              a              |              b              |              c              |              d              |              e              |              f              |
|:-:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|:---------------------------:|
|   | <font color="gray">0</font> | <font color="gray">1</font> | <font color="gray">2</font> | <font color="gray">3</font> | <font color="gray">4</font> | <font color="gray">5</font> | <font color="gray">6</font> |
| a | <font color="gray">1</font> |              0              |              1              |              2              |              3              |              4              |              5              |
| z | <font color="gray">2</font> |              1              |              1              | <font color="red">2</font>  |              0              |              0              |              0              |
| c | <font color="gray">3</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| e | <font color="gray">4</font> |              0              |              0              |              0              |              0              |              0              |              0              |
| d | <font color="gray">5</font> |              0              |              0              |              0              |              0              |              0              |              0              |


## Complexity

---

Time Complexity: __Big-O(n<sup>2</sup>)__
<br>
Space Complexity: __Big-O(n<sup>2</sup>)__

## Source Code

---

