**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<string> findRelativeRanks(vector<int>& score) {
        vector<int> temp = score;
        sort(temp.begin(), temp.end(), [](int a, int b){return a > b;});

        vector<string> ans;
        for (int i = 0; i < score.size(); ++i) {
            int j = 0;
            for ( ; j < score.size(); ++j) {
                if (score[i] == temp[j]) {
                    break;
                }
            }
            if (j == 0) {
                ans.push_back("Gold Medal");
            } else if (j == 1) {
                ans.push_back("Silver Medal");
            } else if (j == 2) {
                ans.push_back("Bronze Medal");
            } else {
                ans.push_back(to_string(j+1));
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел, нужно определить числа по порядку. Вернуть массив, который говорит настоящую позицию числа.
	Решение: Сохранить копию и отсортировать массив. Проходится и проверять на каком месте находится это число.