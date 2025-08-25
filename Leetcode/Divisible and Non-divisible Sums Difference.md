Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int differenceOfSums(int n, int m) {
        return (n*(n+1)/2) - 2 * (m*(n/m)*((n/m)+1)/2);
    }
};
```
**Explanation:**
	Цель: ...
	Решение: 
		Sum of all numbers from 1 to n: total_sum = n * (n + 1) / 2
		num2(Sum of divisible by m) :  
		These are m, 2m, 3m, ..., km where k = n // m  
		This equals m * (1 + 2 + 3 + ... + k) = m * k * (k + 1) / 2
		num1(Sum of numbers not divisible by m): total_sum - num2
		Final answer: num1 - num2 = (total_sum - num2) - num2 = total_sum - 2 × num2