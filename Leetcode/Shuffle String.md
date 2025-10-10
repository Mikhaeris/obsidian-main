**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    string restoreString(string s, vector<int>& indices) {
        int n = s.length();

        string ans(n, '\0');
        for (int i = 0; i < n; ++i) {
            ans[indices[i]] = s[i];
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дана строки и массив чисел, где каждый элемент соотвествует праивльному нахождению i-го элемента в строке. НУжно вернуть правильну строку.
	Pешение: Проходится по новой строке и вставлять на i-ю позицию правильный символ.