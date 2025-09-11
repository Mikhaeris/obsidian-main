**Complexity:** Easy
Answer:
	Time Complexity: O(~3N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	string sortVowels(string& s) {
		string temp;
		for (auto& ch : s) {
			if (isVowel(ch)) {
				temp += ch;
			}
		}
		  
		sort(temp.begin(), temp.end());
		  
		int i = 0;
		for (auto& ch : s) {
			if (isVowel(ch)) {
				ch = temp[i++];
			}
		}
		  
		return s;
	}
private:
	bool isVowel(char& ch) {
		return ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u' ||
		  	   ch == 'A' || ch == 'E' || ch == 'I' || ch == 'O' || ch == 'U';
	}
};
```
**Explanation:**
	Цель: Дана строка, в ней нужно отсортировать все гласные
	Решение: Сохранить все гласные в массиве, отсортировать и потом вставить обратно в строку. Вернуть эту же строку.
	P.S. можно решить немного по другому. считать - считать количество повторений гласных. Потом вставлять их в отсортированном порядке в исхожную строку.
