**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int possibleStringCount(string word) {
		int ans = 0;
		for (int i = 1; i < word.size(); i++) {
			if (word[i] == word[i-1]) {
				ans++;
			}
		}
		return ++ans;
	}
};
```
**Explanation:**
	Цель: Сложно объяснить. Но данга строка в которой повторяются символы, нужно посчитать комбинации которые могут быть из этих символов.
	Решение: Считать повторение и прибавлять. В конрце добавить первоночальное слово.