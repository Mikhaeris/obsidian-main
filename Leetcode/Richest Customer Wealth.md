**Complexity:** Medium
**Task:**
	En: You are given an `m x n` integer grid `accounts` where `accounts[i][j]` is the amount of money the `i​​​​​​​​​​​th​​​​` customer has in the `j​​​​​​​​​​​th`​​​​ bank. Return _the **wealth** that the richest customer has._
	A customer's **wealth** is the amount of money they have in all their bank accounts. The richest customer is the customer that has the maximum **wealth**.
	Ru: Вам дана целочисленная матрица размером m × n `accounts`, где `accounts[i][j]` — сумма денег i-го клиента в j-м банке. Верните богатство, которым обладает самый богатый клиент.
	Богатство клиента — это сумма денег, имеющихся у него на всех банковских счетах. Самым богатым клиентом является тот, у которого максимальное богатство.
	
**Example:**
	**Example 1:**
		**Input:** accounts = [ [1,2,3],[3,2,1] ]
		**Output:** 6
		**Explanation**:
		*1st customer has wealth = 1 + 2 + 3 = 6
		2nd customer has wealth = 3 + 2 + 1 = 6
		Both customers are considered the richest with a wealth of 6 each, so return 6.
	**Example 2:**
		**Input:** accounts = [ [1,5],[7,3],[3,5] ]
		**Output:** 10
		**Explanation**: 
		1st customer has wealth = 6
		2nd customer has wealth = 10 
		3rd customer has wealth = 8
		The 2nd customer is the richest with a wealth of 10.
	**Example 3:**
		**Input:** accounts = [ [2,8,7],[7,1,3],[1,9,5] ]
		**Output:** 17

**Constraints:**
	`m == accounts.length`
	`n == accounts[i].length`
	`1 <= m, n <= 50`
	`1 <= accounts[i][j] <= 100`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maximumWealth(vector<vector<int>>& accounts, int maxSum = 0, int tempSum = 0) {
        for (int i = 0; i < accounts.size(); ++i) {
            tempSum = 0;
            for (int j = 0; j < accounts[0].size(); ++j) {
                tempSum += accounts[i][j];
            }
            if (tempSum > maxSum) {
                maxSum = tempSum;
            }
        }
        return maxSum;
    }
};
```
**Explanation:**
	Цель: Найти максимальную сумму в строках
	Решение: Просто посчитать каждую и сравнить с максимальной в данный момент.