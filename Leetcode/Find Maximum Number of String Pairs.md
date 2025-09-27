**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximumNumberOfStringPairs(vector<string>& words) {
		unordered_set<string> st;
		int count_pairs = 0;
		for (const auto& word : words) {
			string rev_word = word;
			reverse(rev_word.begin(), rev_word.end());
			if (st.find(rev_word) != st.end()) {
				++count_pairs;
				st.erase(word);
			} else {
				st.insert(word);
			}
		}
		return count_pairs;
	}
};
```
**Explanation:**
	Цель: Дан массв строк. Нужно найти найти сколько пар есть в массиве, если i < j и j - перевернутая строка.
	Pешение: Если в хэш такблице нету пары, то добавлять эту строку, если пара есть, то удалять эту строку из хэш таблицы и увеличивать счетчик..