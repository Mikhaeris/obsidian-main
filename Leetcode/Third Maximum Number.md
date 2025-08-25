**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int thirdMax(vector<int>& nums) {
		long long first = LLONG_MIN, second = LLONG_MIN, third = LLONG_MIN;
		for (const auto& num : nums) {
			if (num == first || num == second || num == third) {
				continue;
			}
			  
			if (num > first) {
				third = second;
				second = first;
				first = num;
			}
			else if (num > second) {
				third = second;
				second = num;
			}
			else if (num > third) {
				third = num;
			}
		}
		  
		return (third == LLONG_MIN) ? first : third;
	}
};
```
**Explanation:**
	Цель: Найти третье макимальное число, если его нет вывести макимальное.
	Решение: Три переменные, просто менять их.
	P.S. есто много решений, но это самое быстрое и экономичное.