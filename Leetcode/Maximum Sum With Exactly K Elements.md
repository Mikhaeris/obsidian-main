**Complexity:** Easy
Answer:
	Time Complexity: O(N+M)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maximizeSum(vector<int>& nums, int k) {
        int max_el = 0;
        for (const auto& n : nums) {
            max_el = max(max_el, n);
        }

        int m = 0;
        for (int i = 0; i < k; ++i) {
            m += max_el;
            ++max_el;
        }

        return m;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел и чсило k. Нужно найти максимальную сумму совершая только этот порядок действий: Выбрать число m, удалить его из массива, добавить это m + 1 обратно в массив и увеличить счутчик на m.
	Pешение: Найти максимальное число и провести с ним k увеличений, на каждом хое увеличивая счетчик.