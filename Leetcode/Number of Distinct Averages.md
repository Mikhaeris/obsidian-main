**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int distinctAverages(vector<int>& nums) {
		sort(nums.begin(), nums.end());
		int l = 0, r = nums.size()-1;
		set<double> st;
		while (l < r) {
			st.insert((static_cast<double>(nums[l++])+nums[r--])/2);
		}
		return st.size();
	}
};
```
**Explanation:**
	Цель: выбрать макимальное и минмиальное число, найти их среднее. Узнать сколько различных средних получится.
	Решение: Отсортировтаь массив и с помощью двух указателей брать минмиальное и максимлаьное число и добавлять их среднее в сет. Пройтись по всему парам таких чисел и вернуть ответ.