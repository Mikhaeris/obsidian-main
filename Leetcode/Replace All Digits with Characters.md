**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	string replaceDigits(string& s) {
		for (int i = 1; i < s.length(); i += 2) {
			s[i] = s[i-1] + (s[i] - '0');
		}
		return s;
	}
};
```
**Explanation:**
	Цель: Дана строка. На четных позициях стоят буквы, а на нечетных цифры. Нужно заменить цифры на буквы. Берется буква пред этой цифрой и двигается вправо на значение этой цифры.
	Решение: Пройтись по цифрам и изменить их по правилам
