**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(2N)
Code:
Solution:
```cpp
class Solution {
public:
	int uniqueMorseRepresentations(vector<string>& words) {
		vector<string> alph = { ".-", "-...", "-.-.", "-..",
								".", "..-.", "--.", "....",
								"..", ".---", "-.-", ".-..",
								"--", "-.", "---", ".--.",
								"--.-", ".-.", "...", "-",
								"..-", "...-", ".--", "-..-",
								"-.--", "--.."};
		unordered_set<string> st;
		  
		for (const auto& word : words) {
			string morze;
			for (const auto& ch : word) {
				morze += alph[ch - 'a'];
			}
			st.insert(morze);
		}
		return st.size();
	}
};
```
**Explanation:**
	Цель: Даны слова, нужно вроверить их уникальность по таблице морзе.
	Pешение: Записывать все зашифорванные слова в хеш таблицу. После вернуть ее размер.
