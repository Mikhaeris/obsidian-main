**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int findMaxConsecutiveOnes(vector<int>& nums) {
		int max_n = 0, count = 0;
		for (const auto& num : nums) {
			if (num) {
				++count;
			}
			else {
				max_n = max(max_n, count);
				count = 0;
			}
		}
		  
		return max(max_n, count);
	}
};
```
**Explanation:**
	Цель: Найти больший ряд из едениц и вернуть его.
	Решение: Просто считать и находит макисмальное.
