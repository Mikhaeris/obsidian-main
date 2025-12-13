**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string reverseOnlyLetters(string& s) {
        char* l = &s[0];
        char* r = &s[s.size()-1];
        while (l < r) {
            if (!letter(l)) {
                ++l;
            } else if (!letter(r)) {
                --r;
            } else {
                swap(*l++, *r--);
            }
        }
        return s;
    }
private:
    bool letter(const char* ch) {
        return ('a' <= *ch && *ch <= 'z') || ('A' <= *ch && *ch <= 'Z');
    }
};
```
**Explanation:**
	Цель: Дана строка из строк и символов. Нужно перверунть в ней только буквы.
	Pешение: Два указателя - левый и правый. Проходится и менять только буквы.