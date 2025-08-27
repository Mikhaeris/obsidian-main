**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int minStartValue(vector<int>& nums) {
		int start_value = 0, sum = 0;
		for (const int& num : nums) {
			sum += num;
			start_value = min(start_value, sum);
		}
		  
		return abs(start_value) + 1;
	}
};
```
**Explanation:**
	Цель: Дан массив чисел, нужно найти такое стартовой число, которое при сложение каждого жлемента массива по очередно не опустится ниже еденицы.
	Решение: Две переменные, которая хранит минимальную сумма и текущую сумма. В конце минимальную сумму превратить в положительное число и прибавить еденицу.