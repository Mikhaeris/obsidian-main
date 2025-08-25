**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
static const unordered_map<char, char> vowel_сharacters = {
{'a', '1'}, {'e', '1'}, {'i', '1'}, {'o', '1'}, {'u', '1'} };
  
class Solution {
public:
    int maxVowels(string& s, int k) {
  
        int answer = 0;
  
        for (int i = 0; i < k; ++i) {
            if (vowel_сharacters.find(s[i]) != vowel_сharacters.end()) {
                ++answer;
            }
        }
  
        int temp_count = answer;
        for (int i = k; i < s.size(); ++i) {
            if (vowel_сharacters.find(s[i-k]) != vowel_сharacters.end()) {
                --temp_count;
            }
            if (vowel_сharacters.find(s[i]) != vowel_сharacters.end()) {
                ++temp_count;
            }
  
            if (answer < temp_count) {
                answer = temp_count;
            }
        }
  
        return answer;
    }
};
```
**Explanation:**
	Цель: Дано окно, которое двигается вправо и нужно найти такое, где больше всего гласных букв и вернуть это число.
	Решение: Посчитать количество гласных в первом окне.
	Потом двигать окно и убавлять если слева гласная и прибавлять если справа гласная.