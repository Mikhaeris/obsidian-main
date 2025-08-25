**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string reverseVowels(string s) {
        unordered_map<char, char> vowel_сharacters = {
            {'a', '1'}, {'e', '1'}, {'i', '1'}, {'o', '1'}, {'u', '1'},
            {'A', '1'}, {'E', '1'}, {'I', '1'}, {'O', '1'}, {'U', '1'},
        };
  
        int left = 0, right = s.size() - 1;
        while (left < right) {
            while (left < right && vowel_сharacters.find(s[left]) == vowel_сharacters.end()) {
                ++left;
            }
            while (left < right && vowel_сharacters.find(s[right]) == vowel_сharacters.end()) {
                --right;
            }
  
            swap(s[left], s[right]);
            ++left;
            --right;
        }
  
        return s;
    }
};
```
**Explanation:**
	Цель: В данной строке перевернуть все согласные буквы.
	Решение: Решение с двумя указателями.
	Двигать левый и правый пока не встретится гласная, потом менять местами эти буквы(символы), после сдвигать указатели друг другу на встречу.