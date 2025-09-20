**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	int maxFrequencyElements(vector<int>& nums) {
		unordered_map<int, int> mp;
		int max_freq = 0;
		for (const auto& num : nums) {
			max_freq = max(max_freq, ++mp[num]);
		}
		  
		int ans = 0;
		for (const auto& pr : mp) {
			if (pr.second == max_freq) {
				ans += pr.second;
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно узнать сколько элементов в массив повторяются чаще всего.
	Решение: Считать сколько раз повторяется каждый элемент в массиве и самую большую частоту повторения. Пройтись по хэш таблице и считать количество элементов, котыре повторяются больше всего. Вернуть ответ.