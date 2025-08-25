**Complexity:** Easy
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
	Цель: Вернуть такие слова, что все буквы находсят в одной строке клавиатуры.
	Решение: Абсолютно странная задача. Самый быстрый вариант как мне кажется это хеш таблица, где каждой букве соответсвует ее ряд, скорость моментальная, но память страдает.
	Проходится по кждому слову, брать значение первой буквы и если проверять со всеми остальными буквами, если все буквы из одного ряда, то добавлять это слово в новый массив и так далее. Вернуь этот массив.