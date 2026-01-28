**Complexity:** Easy  
Answer:  
- Time Complexity: O(N^2)
- Space Complexity: O(1)

Code:  
```cpp
class Solution {
public:
    int maxLengthBetweenEqualCharacters(string s) {
        int length = -1;
        for (int i = 0; i < s.length(); ++i) {
            for (int j = i + 1; j < s.length(); ++j) {
                if (s[i] == s[j]) {
                    length = max(length, j - i - 1);
                }
            }
        }
        return length;
    }
};
```
**Explanation:**
- Цель: Дана строка, нужно найти в ней самую длинную подстроку между двумя одинаковыми символами.
- Pешение: Просто пройтись в двойном цикле в поисках одинаковых символов.