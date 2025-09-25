**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(k)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> maxKDistinct(vector<int>& nums, int k) {
		sort(nums.begin(), nums.end(), [](int a, int b){
			return a > b;
		});
		
		vector<int> ans;
		int i = 1;
		for ( ; i < nums.size() && k; ++i) {
			if (nums[i-1] != nums[i]) {
				ans.push_back(nums[i-1]);
				--k;
			}
		}
		if (k) {
			ans.push_back(nums[i-1]);
		}
		return ans;
	}
};
```
**Explanation:**
	Цель: Найти первые k максимальных неповторяющихся элементов.
	Pешение: Отсортировтаь массив в обратном порядке. И добавлять в массив ответа, только неповторяющиеся k элементов.