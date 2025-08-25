**Complexity:** Easy
**Task:**
	En: You are given a string array `words` and a **binary** array `groups` both of length `n`, where `words[i]` is associated with `groups[i]`.
	Your task is to select the **longest alternating**
	from `words`. A subsequence of `words` is alternating if for any two consecutive strings in the sequence, their corresponding elements in the binary array `groups` differ. Essentially, you are to choose strings such that adjacent elements have non-matching corresponding bits in the `groups` array.
	Formally, you need to find the longest subsequence of an array of indices `[0, 1, ..., n - 1]` denoted as `[i0, i1, ..., ik-1]`, such that `groups[ij] != groups[ij+1]` for each `0 <= j < k - 1` and then find the words corresponding to these indices.
	Return _the selected subsequence. If there are multiple answers, return **any** of them._
	**Note:** The elements in `words` are distinct.
	Ru: Вам дан массив строк `words` и бинарный массив `groups`, оба длины `n`, где `words[i]` связано с `groups[i]`.
	Ваша задача — выбрать **самую длинную чередующуюся подпоследовательность** из массива `words`. Подпоследовательность считается чередующейся, если для любых двух последовательных строк в этой последовательности соответствующие им элементы из массива `groups` различаются. По сути, нужно выбрать такие строки, чтобы соседние элементы имели **разные значения битов** в массиве `groups`.
	Формально, требуется найти самую длинную подпоследовательность массива индексов `[0, 1, ..., n - 1]`, обозначаемую как `[i0, i1, ..., ik-1]`, такую, что `groups[ij] != groups[ij+1]` для каждого `0 <= j < k - 1`, а затем получить строки из `words`, соответствующие этим индексам.
	Верните выбранную подпоследовательность. Если существует несколько правильных ответов — верните любой из них.
	**Примечание:** элементы в массиве `words` уникальны (не повторяются).
	
**Example:**
	**Example 1:**
		**Input:** words = ["e","a","b"], groups = [0,0,1]
		**Output:** ["e","b"]
		**Explanation:**
		A subsequence that can be selected is `["e","b"]` because `groups[0] != groups[2]`. Another subsequence that can be selected is `["a","b"]` because `groups[1] != groups[2]`. It can be demonstrated that the length of the longest subsequence of indices that satisfies the condition is `2`.
	**Example 2:**
		**Input:** words = ["a","b","c","d"], groups = [1,0,1,1]
		**Output:** ["a","b","c"]
		**Explanation:**
		A subsequence that can be selected is `["a","b","c"]` because `groups[0] != groups[1]` and `groups[1] != groups[2]`. Another subsequence that can be selected is `["a","b","d"]` because `groups[0] != groups[1]` and `groups[1] != groups[3]`. It can be shown that the length of the longest subsequence of indices that satisfies the condition is `3`.
**Constraints:**
	`1 <= n == words.length == groups.length <= 100`
	`1 <= words[i].length <= 10`
	`groups[i]` is either `0` or `1.`
	`words` consists of **distinct** strings.
	`words[i]` consists of lowercase English letters.
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution 1:
```cpp
class Solution {
public:
    vector<string> getLongestSubsequence(vector<string>& words, vector<int>& groups) {
        if (groups.size() == 1) {
            return words;
        }

        for (int i = 0; i < groups.size()-1; ++i) {
            if (groups[i] == groups[i+1]) {
                words.erase(words.begin() + i + 1);
                groups.erase(groups.begin() + i + 1);
                --i;
            }
        }
        return words;
    }
};
```
**Explanation:**
	Цель: Есть два массива words[i] == groups[i], groups содержит еденицы и нули. Нужно найти такую цепочку(последовательность), в которой будут чередоваться еденицы и нули(например [1,0,1,0,1,...]) и чтобы она была наибольшей длины.
	Решение: Проходится по каждому элементу и сравнивать со следующим, если следующий равен этому, то удалять следующий. Не забывая индекс уменьшать на один.
	Т.е. как бы происходит вырезание повторяющихся подряд цифр.