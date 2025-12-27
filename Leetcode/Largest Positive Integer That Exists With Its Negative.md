**Complexity:** Easy
Answer:
	Time Complexity: O(N\*log(N)+N+N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int findMaxK(vector<int>& nums) {
        sort(nums.begin(), nums.end(), [&](const auto a, const auto b){ return a > b; });
        unordered_map<int, bool> mp;
        for (const auto& n : nums) {
            if (n > 0) {
                mp[n] = false;
            } else if (mp.find(abs(n)) != mp.end()) {
                mp[abs(n)] = true;
            }
        }
        
        int max_n = 0;
        for (const auto& pr : mp) {
            if (pr.second == true && max_n < pr.first) {
                max_n = pr.first;
            }
        }

        return (max_n != 0) ? max_n : -1;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно найти в нем такое максимальное число, что в этом ассиве содержится его отрицаительная форма.
	Pешение: Отсортировать массив по убыванию. Заполнять хэш таблицу числом и если есть его отрицаительное, то значение true. Проходится по хэш таблице и искать такие числа, у котрых есть отрицательная форма в числе и искать максимальное. Если такого числа нет, то возвращать -1.
