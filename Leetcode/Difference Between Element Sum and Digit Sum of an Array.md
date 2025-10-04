**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution1:
```cpp
class Solution {
public:
	int differenceOfSum(vector<int>& nums) {
	    int el_sum = 0, dig_sum = 0;
	    for (auto& num : nums) {
	        el_sum += num;
	
	        do {
	            dig_sum += num % 10;
	        } while (num /= 10);
	    }
	    return abs(el_sum - dig_sum);
	}
};
```
**Explanation:**
	Цель: Найти разницу по модулю между сумму элементов и суммой цифр в массиве.
	Решение: Посчитать сумму елементов и цифр. Вернуть разницу по модулю.