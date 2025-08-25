**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string mergeAlternately(string word1, string word2) {
        string answer = "";
        int minWord = min(word1.size(), word2.size());
        for (int i = 0; i < minWord*2; ++i) {
            if (i % 2) {
                answer.push_back(word2[i / 2]);
            }
            else {
                answer.push_back(word1[i / 2]);
            }
        }
        if (word1.size() < word2.size()) {
            answer += word2.substr(minWord, word2.size() - minWord);
        }
        else if (word1.size() > word2.size()) {
            answer += word1.substr(minWord, word1.size() - minWord);
        }
        return answer;
    }
};
```
**Explanation:**
	Цель: Объеденить две строки, чередованием символов. Если какая-то строка длинее, то ее хвост добавляется в конец.
	Решение: Вычислить длину минмального слова. Проходится по двум строкам одновременно в цикле до минимальное количество умноженное на два. Проверяя делимость на два, чередуются слова.
	В конце добавить хвост.