**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(26)
Code:
Solution:
```cpp
class Solution {
public:
	int canBeTypedWords(string text, string brokenLetters) {
		char alph[26] = {0};
		for (const auto& ch : brokenLetters) {
			alph[ch - 'a'] = 1;
		}
		  
		int count = 0;
		bool take = true;
		for (int i = 0; i <= text.length(); ++i) {
			char ch = text[i];
			if ((ch == ' ' || ch == '\0') && take) {
				++count;
			} else if ((ch != ' ' && ch != '\0')) {
				if (alph[ch - 'a']) {
					take = false;
				}
			}
			  
			if (ch == ' ') {
				take = true;
			}
		}
		  
		return count;
	}
};
```
**Explanation:**
	Цель: Дан желаемый текст и сломанные буквы. Нужно узнать скольок слов получится напечатать.
	Pешение: Записать все сломанные буквы в массив из 26 элементов. Далее проходится по словам и проверять если ли в словах сломанные буквы, если нет, то слово подходит. Вернуть количество возможных слов.
