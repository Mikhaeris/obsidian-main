**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string truncateSentence(string& s, int& k) {
        for (int i = 0, count_spaces = 0; i < s.size(); ++i) {
            if (s[i] == ' ') {
                ++count_spaces;
                if (count_spaces == k) {
                    s.resize(i);
                    break;
                }
            }
        }
  
        return s;
    }
};
```
**Explanation:**
	Цель: Дано предложение и число k. Нужно вернуть предложение, в котором содердится только первые k слов.
	Решение: Считать количество пробелов, если оно равно числу k, то отрезать справа часть.