**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> separateDigits(vector<int>& nums) {
		vector<int> ans;
		string temp;
		for (int& n : nums) {
			if (n / 10 == 0) {
				ans.push_back(n);
			} else {
				temp = to_string(n);
				for (int i = 0; i < temp.size(); ++i) {
					ans.push_back(temp[i] - '0');
				}
			}
		}
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан вектор чисел. Нужно вернуть массив, разбитых чисел на цифры, в том порядке, в котором они даны.
	Решение: Если одна цифра, то записать, иначе записать число в строку и записывать чсила из строки в массив сначала.
