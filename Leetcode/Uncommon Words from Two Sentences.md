**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	vector<string> uncommonFromSentences(string s1, string s2) {
		unordered_map<string, int> mp;
		  
		string temp;
		for (int i = 0; i < s1.length(); ++i) {
			if (s1[i] == ' ') {
				++mp[temp];
				temp = "";
				continue;
			}
			temp += s1[i];
		}
		++mp[temp];
		temp = "";
		  
		for (int i = 0; i < s2.length(); ++i) {
			if (s2[i] == ' ') {
				++mp[temp];
				temp = "";
				continue;
			}
			temp += s2[i];
		}
		++mp[temp];
		  
		vector<string> ans;
		for (const auto& pr : mp) {
			if (pr.second == 1) {
				ans.push_back(pr.first);
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Даны две строки. Нужно найти в них слова которые не повторяются.
	Решение: Записывать все слова в [[Hash table]] и после пройтись по таблице, добавляяя в ans только слова, которые не повторяются.
