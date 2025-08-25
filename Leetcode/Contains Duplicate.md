**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool containsDuplicate(vector<int>& nums) {
		unordered_map<int, int> mp;
		for (int i = 0; i < nums.size(); i++) {
			mp[nums[i]]++;
			if (mp[nums[i]] > 1) {
				return true;
			}
		}
		return false;
	}
};
```
**Explanation:**
	Цель: Узнать есть ли дупликаты в векторе.
	Решение: Создать хеш-таблицу [[Hash table]]. Записывать ключ-число, значение-количество повторов. На каждой итерации проверять если количество повторов больше одного, то останавливать.

Answer2:
	Time Complexity: O(N*\N*\log(N))
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool containsDuplicate(vector<int>& nums) {
		sort(nums.begin(), nums.end());
		for (int i = 0; i < nums.size()-1; i++) {
			if (nums[i] == nums[i+1]) {
				return true;
			}
		}
		return false;
	}
};
```
**Explanation:**
	Цель: Узнать есть ли дупликаты в векторе.
	Решение: Отсортировать массив. Проверять, если этот элемент равен следующему, то останавливать.