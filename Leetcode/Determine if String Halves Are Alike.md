**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool halvesAreAlike(string s) {
        int lv = 0, rv = 0;

        int l = 0, r = s.length()-1;
        while (l < r) {
            if (isVowel(s[l])) {
                ++lv;
            }
            if (isVowel(s[r])) {
                ++rv;
            }
            ++l, --r;
        }
        
        return lv == rv;
    }
private:
    bool isVowel(const char& ch) {
        return (ch == 'a') || (ch == 'e') || (ch == 'i') || (ch == 'o') || (ch == 'u') ||
               (ch == 'A') || (ch == 'E') || (ch == 'I') || (ch == 'O') || (ch == 'U');
    }
};
```
**Explanation:**
	Цель: Дана строка четной длины нужно проверить что слева и справа одинаковое количество гласных букв.
	Pешение: Проходится двумя указателями слева и справа и считать колчиество гласных букв. Вернуть ответ.