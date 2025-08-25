**Complexity:** Medium
**Task En:**
	You have two types of tiles: a `2 x 1` domino shape and a tromino shape. You may rotate these shapes.
	![](https://assets.leetcode.com/uploads/2021/07/15/lc-domino.jpg)
	Given an integer n, return _the number of ways to tile an_ `2 x n` _board_. Since the answer may be very large, return it **modulo** `10^9 + 7`.
	In a tiling, every square must be covered by a tile. Two tilings are different if and only if there are two 4-directionally adjacent cells on the board such that exactly one of the tilings has both squares occupied by a tile.
**Task Ru:** 
	У вас есть два типа плиток: **домино размером 2×1** и **тромино**. Эти плитки можно поворачивать.
	Дано целое число `n`. Верните количество способов замостить доску размером **2×n**. Поскольку ответ может быть очень большим, верните его по модулю **10⁹ + 7**.
	В замощении каждая клетка доски должна быть покрыта плиткой. **Два замощения считаются различными** **только в том случае**, если на доске найдутся две клетки, смежные по четырём направлениям (вверх, вниз, влево, вправо), такие что **только в одном из замощений обе клетки покрыты одной плиткой**.

**Example:**
	**Example 1:**
	![](https://assets.leetcode.com/uploads/2021/07/15/lc-domino1.jpg)
		**Input:** n = 3
		**Output:** 5
		**Explanation:**
		The five different ways are show above.
	**Example 2:**
		**Input:** n = 1
		**Output:** 1
**Constraints:**
	`1 <= n <= 1000`
	
**Answer:**
	Resources:
		Time Complexity: O(n)
		Space Complexity: O(n)
Code:
```cpp
class Solution {
public:
    const int mod = 1e9 + 7;

    int numTilings(int n) {
        if (n <= 1) return 1;
        if (n == 2) return 2;
        if (n == 3) return 5;
        
        vector<int> dp(n+1, 0);
        dp[0] = 1, dp[1] = 1, dp[2] = 2, dp[3] = 5;
        for (int i = 4; i <= n; i++)
            dp[i] = (dp[i-1]*2 + long(dp[i-3])) % mod;
	        return dp[n];
    }
};
```

**Explanation:**
	Цель: Найти все возможные расстановки на площади 2\*n доминошек и троминошек(тромино что?)
	Решение: Для начала эта задача про последовательности(по типу Фибоначи).
	Нужно найти эту последовательность(например порсивоть хотя бы до n = 5, при n = 6 - 117 вариантов :) ). Дальше найти закономерность и вывести формулу последовательности. В данном случае это: **f(n) = f(n-1)\*2 + f(n-3)**.
	Первый варинат рекурсивно пройтись, но дерево рекурсии будет очень большим и тем более одни значения будут вычисляться по несколько раз(например return 1 будет вызыватья более 100 раз:) ). Поэтому стоить сделать по другому
	Так как любую рекурсивную задачу можно решить циклом и наоброт. То можно создать массив со всеми вычисляемыми значениями и заполнять его по n-ый элемент. И вернуть n-ый элемент.
	Так же не забыть про нахождения остатка от `10^9 + 7`