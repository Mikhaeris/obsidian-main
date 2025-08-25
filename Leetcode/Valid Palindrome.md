**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool isPalindrome(string s) {
        int l = 0, r = s.size()-1;
        while (l < r) {
            while (l < s.size()-1 && !isalnum(s[l])) {
                ++l;
            }

            if (!islower(s[l])) {
                s[l] += 'a' - 'A';
            }

            while (r > 0 && !isalnum(s[r])) {
                --r;
            }
            
            if (!islower(s[r])) {
                s[r] += 'a' - 'A';
            }

            if (s[l] != s[r]) {
                return false;
            }

            ++l, --r;
        }

        return true;
    }
};
```
**Explanation:**
	Цель: Проверить, является ли строка палиндромом, пропуская все символы кроме букв и цифр.
	Решение: Два указателя, сравнивают символы сначала и с конца. Пропускать все не символы и не буквы. Если буква в верхнем регистре, то переделывать в нижний.

Solution2:
```cpp
bool isPalindrome(string s) {
	char *l = &s[0], *r = &s[s.size()-1];
	while (l < r) {
		while (l <= r && !isalnum(*l++))
			;

		if (!islower(*--l))
			*l += 32;

		while (l <= r && !isalnum(*r--))
			;
	
		if (!islower(*++r))
			*r += 32;

		if (*l++ != *r--)
			return false;
	}

	return true;
}
```