**Complexity:** Easy
**Task:**
	En: You are given a **0-indexed** array of strings `words` and a character `x`.
	Return _an **array of indices** representing the words that contain the character_ `x`.
	**Note** that the returned array may be in **any** order.
	Ru: Вам дан массив строк `words` с нумерацией с нуля и символ `x`.  
	Верните массив индексов, представляющих слова, которые содержат символ `x`.  
	Обратите внимание, что возвращаемый массив может быть в любом порядке.
	
**Example:**
	**Example 1:**
		**Input:** words = ["leet","code"], x = "e"
		**Output:** [0,1]
		**Explanation:** "e" occurs in both words: "l**ee**t", and "cod**e**". Hence, we return indices 0 and 1.
	**Example 2:**
		**Input:** words = ["abc","bcd","aaaa","cbc"], x = "a"
		**Output:** [0,2]
		**Explanation:** "a" occurs in "**a**bc", and "**aaaa**". Hence, we return indices 0 and 2.
	**Example 3:**
		**Input:** words = ["abc","bcd","aaaa","cbc"], x = "z"
		**Output:** []
		**Explanation:** "z" does not occur in any of the words. Hence, we return an empty array.

**Constraints:**
	`1 <= words.length <= 50`
	`1 <= words[i].length <= 50`
	`x` is a lowercase English letter.
	`words[i]` consists only of lowercase English letters.
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> findWordsContaining(vector<string>& words, char x) {
        vector<int> answer;
        for (int i = 0; i < words.size(); ++i) {
            for (const auto& character : words[i]) {
                if (character == x) {
                    answer.push_back(i);
                    break;
                }
            }
        }
        return answer;
    }
};
```
**Explanation:**
	Цель: Найти все слова, где есть данная буква.
	Решение: Пройтись по каждому слову в поиске буквы. Если буква найдена, то записать в массив и перейти к другому слову.