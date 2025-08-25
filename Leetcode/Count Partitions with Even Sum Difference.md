**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int countPartitions(vector<int>& nums) {
		int r_sum = 0;
		for (const auto& num : nums) {
			r_sum += num;
		}
		  
		int ans = 0;
		int l_sum = 0;
		for (int i = 0; i < nums.size()-1; ++i) {
			l_sum += nums[i];
			r_sum -= nums[i];
			  
			if ((l_sum - r_sum) % 2 == 0) {
				++ans;
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно найти такие подмассивы(что 0 - i и i+1 - n-1), что разница между подмассивами четная.
	Решение: Получить сумму всего массива. Дальше собирать сумму слева и вычистать из правой суммы по элементу и смотреть на четность разницы(идти до предпосленего элемента).