**Complexity:** Easy
Answer:
	Time Complexity: O(2N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool isSumEqual(string firstWord, string secondWord, string targetWord) {
		int first = 0;
		for (const auto& ch : firstWord) {
			first = first * 10 + (ch - 'a');
		}
	
		int second = 0;
		for (const auto& ch : secondWord) {
			second = second * 10 + (ch - 'a');
		}
	
		int target = 0;
		for (const auto& ch : targetWord) {
			target = target * 10 + (ch - 'a');
		}
		return first + second == target;
    }
};
```
**Explanation:**
	Цель: Дано три слова, нужно переделать в число и сложить первые два и сравнить с третьим.
	Решение: Проходится по слову и переделывать его в число, умножая новое число на 10(т.е. добалять разряд справа) и прибалять вычитание из символа симвоал 'a' - так получается число. Сделать это для трех данных слов и вернуть проверку на равенство.
