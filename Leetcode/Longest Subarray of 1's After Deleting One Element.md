**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int longestSubarray(vector<int>& nums) {
		int ans = 0, count = 0;
		int l = 0, r = 0;
		while (r < nums.size()) {
			if (nums[r] == 0) {
				++count;
			}
			  
			if (count > 1) {
				if (nums[l] == 0) {
					--count;
				}
				++l;
			}
			  
			ans = max(r-l, ans);
			++r;
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Найти самый длинный подмасив, состоящий из едениц, если нужно удалить один элемент.
	Решение: [[Sliding window]] в котором может содержаться один ноль, если количество нулей больше одного, значит нужно двигать левую границу.
	На каждом шаге считать длину подмассива и сохранять если она больше предыдущей максимальной.