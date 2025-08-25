**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<string> removeSubfolders(vector<string>& folder) {
		sort(folder.begin(), folder.end());
		  
		vector<string> ans = { folder[0] };
		for (int i = 1; i < folder.size(); ++i) {
			if ((ans.back() + '/') != folder[i].substr(0, ans.back().size()+1)) {
				ans.push_back(folder[i]);
			}
		}
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив строк, где каждая строка это папка, нужно вернуть массив строк без вложенных папок.
	Решение: Отсортировать массив лексикографически(так как родительские папки станут вперед). Потом искать такие папки, что начало папки не будет равнять предыдущей найденной. И вернуть массив.
	Сложность задачи только в понимании сортировки лекскографически и сравнение префикса строк.