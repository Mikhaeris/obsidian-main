**Complexity:** Medium
**Task:**
	En: You are given an array of strings words. Each element of words consists of two lowercase English letters.
	Create the longest possible palindrome by selecting some elements from words and concatenating them in any order. Each element can be selected at most once.
	Return the length of the longest palindrome that you can create. If it is impossible to create any palindrome, return 0.
	A palindrome is a string that reads the same forward and backward.
	Ru: Вам дан массив строк `words`. Каждый элемент массива `words` состоит из двух строчных английских букв.  
	Создайте максимально возможный палиндром, выбирая некоторые элементы из `words` и конкатенируя их в любом порядке. Каждый элемент можно выбрать не более одного раза.  
	Верните длину самого длинного палиндрома, который вы можете получить. Если невозможно создать ни одного палиндрома, верните 0.  
	Палиндром — это строка, которая читается одинаково слева направо и справа налево.
	
**Example:**
	**Example 1:**
		**Input:** words = ["lc","cl","gg"]
		**Output:** 6
		**Explanation:** One longest palindrome is "lc" + "gg" + "cl" = "lcggcl", of length 6.
		Note that "clgglc" is another longest palindrome that can be created.
	**Example 2:**
		**Input:** words = ["ab","ty","yt","lc","cl","ab"]
		**Output:** 8
		**Explanation:** One longest palindrome is "ty" + "lc" + "cl" + "yt" = "tylcclyt", of length 8.
		Note that "lcyttycl" is another longest palindrome that can be created.
	**Example 3:**
		**Input:** words = ["cc","ll","xx"]
		**Output:** 2
		**Explanation:** One longest palindrome is "cc", of length 2.
		Note that "ll" is another longest palindrome that can be created, and so is "xx".

**Constraints:**
	`1 <= words.length <= 105`
	`words[i].length == 2`
	`words[i]` consists of lowercase English letters.
Answer:
	Time Complexity: O(N\*L)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int longestPalindrome(vector<string>& words) {
        unordered_map<string, int> countMap;
        
        for (const auto& word : words) {
            countMap[word]++;
        }
        
        int lenghtPal = 0, center = 0;
        for (auto& [word, count] : countMap) {
            string revWord = word;
            reverse(revWord.begin(), revWord.end());
            if (word == revWord) {
                lenghtPal += 4 * (count / 2);
                if (count % 2) {
                    center = 1;
                }
            }
            else if (word < revWord && countMap.count(revWord)) {
                lenghtPal += 4 * min(count, countMap[revWord]);
            }
        }
        
        return lenghtPal + center * 2;
    }
};
```
**Explanation:**
	Цель: Составить из слов(состоят из двух букв), перемещая их в любом порядке, самый длинный палиндром
	Решение: Для начала составить хэш-мап, где будет хранится информация о том сколько раз повторяется данное слово.
	Потом нужно пройтись по этой хэш-мапе и смотреть:
		Если первая и вторая буква совпадают, то добавлять 4 умноженное на количество этого слова деленного на 2(потому что нужно четное количество). Если количество не делится на два (т.е. например оно 3), то значит его можно добавить в центр.
		Если первая и вторая буква разные и слово меньше перевернутого слова(т.е так исключается повторение) и в хэш-таблице есть обратное слово для данного, то добавить 4 умноженное на минимальное из двух слов(изначального и обратного).
	Вернуть посчитанное количество и плюс центр, если есть.