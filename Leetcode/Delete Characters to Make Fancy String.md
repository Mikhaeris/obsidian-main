**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
	string makeFancyString(string s) {
		string ans = "";
		ans.push_back(s[0]);
		  
		int count = 1;
		for (int i = 1; i < s.size(); ++i) {
			if (s[i] == s[i-1]) {
				++count;
			}
			else {
				count = 1;
			}
			  
			if (count < 3) {
				ans.push_back(s[i]);
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Есть строка, нужно вернуть такую строку, в которой подряд не будет больше двух одинаковых символов.
	Решение: Создать новую строку и записывать в нее символы без повтором больше двух.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string makeFancyString(string& s) {
		if (s.size() < 3) {
			return move(s);
		}
		  
		int l = 2;
		for (int r = 2; r < s.size(); ++r) {
			if ((s[r] != s[l - 1]) || (s[r]) != s[l -2]) {
				s[l++] = s[r];
			}
		}
		
		s.resize(l);
		return move(s);
	}
};
```
**Explanation:**
	Цель: Есть строка, нужно вернуть такую строку, в которой подряд не будет больше двух одинаковых символов.
	Решение: Зачем сохранять символы в новой строке, если можно делать все на месте. Идея довольно простая и в реалезации тоже. Берем два указателя, один бежит вперед, пропуская повторения, второй записывает все без повторений.
	Решение бьется 100 из 100 и по времени, и по памяти.