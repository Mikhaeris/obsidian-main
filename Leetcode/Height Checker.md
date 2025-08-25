**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int heightChecker(vector<int>& heights) {
		vector<int> expected(heights.begin(), heights.end());
		sort(expected.begin(), expected.end());
		  
		int ans = 0;
		for (int i = 0; i < heights.size(); ++i) {
			if (heights[i] != expected[i]) {
				++ans;
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно посчитать сколько человек стоит не на своем месте(правильный порядок по возрастанию).
	Решение: Создать копию массив, отсортировть и подсчитать сколько человек не на своем месте.