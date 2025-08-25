**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
		sort(s.begin(), s.end());
		sort(t.begin(), t.end());
		
		return s == t;
	}
};
```
**Explanation:**
	Цель: Даны две строки, проверить что они анаграммы.
	Решение: Отсортировать их и сравнить.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isAnagram(string s, string t) {
		if (s.size() != t.size()) {
			return 0;
		}
		
		array<int, 26> arr;
		arr.fill(0);
		  
		for (int i = 0; i < s.size(); ++i) {
			++arr[s[i]-97];
		}
		  
		for (const auto& ch : t) {
			if (arr[ch-97] == 0) {
				return 0;
			}
			--arr[ch-97];
		}
		  
		return 1;
	}
};
```
**Explanation:**
	Цель: Даны две строки, проверить что они анаграммы.
	Решение: В данном случае хранить все буквы первого слова как алфавит.
	Первый цикл заполняет буквы, сколько раз они встречаются. Вторым циклом сверяем количество букв со вторым, если встречается новая буква - значит не подходит, если букв больше - то тоже не подходит, если во втором слове какой-то буквы меньше, чем в первой - значит какой-то ругйо бквы больше - значит сработает условие на другой букве.
