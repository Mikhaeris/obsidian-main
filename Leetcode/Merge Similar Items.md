**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<vector<int>> mergeSimilarItems(vector<vector<int>>& items1, vector<vector<int>>& items2) {
        int arr[1001] = {0};

        for (int i = 0; i < items1.size(); ++i) {
            arr[items1[i][0]] += items1[i][1];
        }

        for (int i = 0; i < items2.size(); ++i) {
            arr[items2[i][0]] += items2[i][1];
        }

        vector<vector<int>> ans;
        for (int i = 0; i < 1001; ++i) {
            if (arr[i] > 0) {
                ans.push_back({i, arr[i]});
            }
        }

        sort(ans.begin(), ans.end());
        return ans;
    }
};
```
**Explanation:**
	Цель: Дано два массива с предметами, их номером и весом. Нужно узнать сумму и вернуть эти предметы в возрастающем порядке.
	Решение: Создать буффер размерность 1001 и прибавлять к нужным индексам нужный вес. Перенести эти номера и вес предметов в другой массив(только которые больше 0) и отсортировтаь его. Вернуть данный массив.