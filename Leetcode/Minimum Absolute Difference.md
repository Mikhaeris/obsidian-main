**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<vector<int>> minimumAbsDifference(vector<int>& arr) {
        int n = arr.size();

        sort(arr.begin(), arr.end());

        int min_diff = arr[1] - arr[0];
        for (int i = 0; i < n-1; ++i) {
            min_diff = min(min_diff, arr[i+1] - arr[i]);
        }

        vector<vector<int>> pairs;
        for (int i = 0; i < n-1; ++i) {
            if (min_diff == (arr[i+1] - arr[i])) {
                pairs.push_back({arr[i], arr[i+1]});
            }
        }

        return pairs;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно найти такие пары, абсолютная разница чисел которых равная минмиальной разнице среди всех чисел.
	Решение: Отсортировать массив чисел. Найти минимальную разницу. Пройтись снова собираю соседние числа, у которых разница равна минимальной.