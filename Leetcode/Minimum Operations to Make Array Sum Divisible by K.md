**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int minOperations(vector<int>& nums, int k) {
		int sum = 0;
		for (const auto& num : nums) {
			sum += num;
		}
		  
		return sum % k;
	}
};
```
**Explanation:**
	Цель: Дан массив чисел и число k, нужно узнать сколько нужно вычесть едениц и чисел массива, чтобы сумма числе в массиве делилась на k, без остатка.
	Pешение: Посчитаь сумму чисел в массиве, вернуть остаток от деления на k.