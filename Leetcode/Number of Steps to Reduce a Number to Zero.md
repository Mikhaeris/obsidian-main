**Complexity:** Medium
**Task:**
	En: Given an integer `num`, return _the number of steps to reduce it to zero_.
	In one step, if the current number is even, you have to divide it by `2`, otherwise, you have to subtract `1` from it.
	Ru: Дано целое число `num`, верните количество шагов, чтобы свести его к нулю.
	За один шаг, если текущее число чётное, вы должны разделить его на 2, в противном случае вы должны вычесть из него 1.
	
**Example:**
	**Example 1:**
		**Input:** num = 14
		**Output:** 6
		**Explanation:** 
		Step 1) 14 is even; divide by 2 and obtain 7. 
		Step 2) 7 is odd; subtract 1 and obtain 6.
		Step 3) 6 is even; divide by 2 and obtain 3. 
		Step 4) 3 is odd; subtract 1 and obtain 2. 
		Step 5) 2 is even; divide by 2 and obtain 1. 
		Step 6) 1 is odd; subtract 1 and obtain 0.
	**Example 2:**
		**Input:** num = 8
		**Output:** 4
		**Explanation:** 
		Step 1) 8 is even; divide by 2 and obtain 4. 
		Step 2) 4 is even; divide by 2 and obtain 2. 
		Step 3) 2 is even; divide by 2 and obtain 1. 
		Step 4) 1 is odd; subtract 1 and obtain 0.
	**Example 3:**
		**Input:** num = 123
		**Output:** 12

**Constraints:**
	`0 <= num <= 106`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int numberOfSteps(int num, int answer = 0) {
        while (num != 0) {
            if (num % 2 == 0) {
                num /=2;
                answer++;
            }
            else {
                num--;
                answer++;
            }
        }
        return answer;
    }
};
```
**Explanation:**
	Цель: Посчитать количество шагов для достижения нуля
	Решение: Просто выполнять данные действия и считать количество шагов.
	Примечание: Возможно есть решение O(1)