**Complexity:** Easy
**Task En:**
	You are given a string `s`. The **score** of a string is defined as the sum of the absolute difference between the **ASCII** values of adjacent characters.
	Return the **score** of `s`.
**Task Ru:** 
	Вам дана строка s. Оценка (score) строки определяется как сумма абсолютных разностей между ASCII-значениями соседних символов.
	Верните оценку строки s.

**Example:**
	**Example 1:**
		**Input:** s = "hello"
		**Output:** 13
		**Explanation:**
		The **ASCII** values of the characters in `s` are: `'h' = 104`, `'e' = 101`, `'l' = 108`, `'o' = 111`. So, the score of `s` would be `|104 - 101| + |101 - 108| + |108 - 108| + |108 - 111| = 3 + 7 + 0 + 3 = 13`.
	**Example 2:**
		**Input:** s = "zaz"
		**Output:** 50
**Constraints:**
	`2 <= s.length <= 100`
	`s` consists only of lowercase English letters.
	
**Answer:**
	Resources:
		Time Complexity: O(n)
		Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int scoreOfString(string s, int score = 0) {
        for (int i = 0; i < s.size()-1; i++)
            score += abs(s[i] - s[i+1]);
        return score;
    }
};
```

**Explanation:**
	Цель: Есть два символа, нужно перевести в ASCII и посчитать их разность по модулю. И так для всех символов в строке
	Решение: Проходится по каждому символу и считать
	модуль(s[i] - s[i-1]), сохраняя все это в score