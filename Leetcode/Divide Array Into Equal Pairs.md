**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool divideArray(vector<int>& nums) {
		unordered_map<int, int> mp;
		for (const auto& num : nums) {
			mp[num]++;
		}
		  
		for (const auto& pair : mp) {
			if (pair.second % 2) {
				return false;
			}
		}
		  
		return true;
	}
};
```
**Explanation:**
	Цель: Проверить, можно из массива сделать пары, где каждое число равно другому.
	[[Hash table]]
	Решение: Составить хэш-таблицу, где хранить количство вхождений чисел в массив. Потом проверять на четность.