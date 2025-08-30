**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int lengthOfLongestSubstring(string s) {
        int alph[96] = {0};
        int max_l = 0;

        int l = 0, r = 0;
        while (r < s.length()) {
            alph[s[r]-' ']++;

            if (alph[s[r]-' '] > 1) {
                max_l = max(max_l, r-l);

                while (alph[s[r]-' '] != 1) {
                    alph[s[l]-' ']--;
                    l++;
                }
            }
            r++;
        }
        max_l = max(max_l, r-l);

        return max_l;
    }
};
```
**Explanation:**
	Цель: Дана строка. Нужно найти такую самую длинную подстроку, в которой символы не повторяются.
	Решение: Создать массив символов с двигом на пробемл(32 символ в таблице).
	С помощью [[Sliding window]]  проходится по строке, прибавляя к каждому символу количество его повторений. Каждый раз когда символ два в окно, то сохранять макимальную лдинну подстроки и двигать левый указатель вправо, пока не станет каждого символа в окне по одному.

Code2:
```cpp
class Solution {
public:
	int lengthOfLongestSubstring(const string& s) {
		char alph[96] = {0};
		int l = 0, r = -1, max_l = 0;
		while (++r < s.length()) {
			if (++alph[s[r]-' '] > 1) {
				max_l = (max_l > r-l) ? max_l : r-l;
				while (--alph[s[l++]-' '] != 1);
			}
		}
		return (max_l > r-l) ? max_l : r-l;
	}
};
```
**Explanation:**
	Объяснение: Все тоже самое, что и в предыдушем коде, только как можно меньше строчек.
	Тут стало еще больше неявного, запутанного, сложно читаемого кода. Но мне просто захотелось такое сделать:)