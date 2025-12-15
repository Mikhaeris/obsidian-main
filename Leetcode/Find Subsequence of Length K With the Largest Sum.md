**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> maxSubsequence(vector<int>& nums, int k) {
        int n = nums.size();
        vector<pair<int, int>> temp(n);
        for (int i = 0; i < n; ++i) {
            temp[i] = {nums[i], i};
        }

        sort(temp.begin(), temp.end(),
            [&](const auto a, const auto b){
                return a.first > b.first;
            });

        sort(temp.begin(), temp.begin() + k,
            [&](const auto a, const auto b){
                return a.second < b.second;
            });

        vector<int> ans(k);
        for (int i = 0; i < k; ++i) {
            ans[i] = temp[i].first;
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив из чисел. Трубуется найти подпоследовательность размером k, что ее сумма максимальна из всех возможных подпоследовательностей.
	Pешение: Копировать изначальный массив в массив пар, где первый элемент это число, а второй его индекс. Отсортировать по убыванию чисел этот массив. Потом в нем отсортировтаь по возрастанию индексов первые k элементов. Копировать числа в вектор ответа. Вернуть массив.