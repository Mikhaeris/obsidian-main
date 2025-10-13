**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<string> removeAnagrams(vector<string>& words) {
        vector<string> ans;

        string prev;
        for (const auto& word : words) {
            string curr = word;
            sort(curr.begin(), curr.end());

            if (prev != curr) {
                ans.push_back(word);
                prev = curr;
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Удалить из данного массива все аннограмы, оставив только первое встречающееся слово в подпоследовательности.
	Pешение: Сохранять предыдущее и сортировать текущее слово. Если они не совпадают, то запихивать в массив текущее слово(т.е. оно первое в текущей подпоследовательности).