**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N+1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> countBits(int n) {
        vector<int> ans(n+1);
        for (int i = 0; i <= n; ++i) {
            int count = 0;
            int ci = i;
            while (ci) {
                ci &= ci -1;
                ++count;
            }
            ans[i] = count;
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дано число, нужно посчитать сколько едениц в каждом числе до этого числа и вернуть массив.
	Решение: Проходится по всем числам и с помощью быстрого алгоритма подсчетов битов в числе Кернигана подсчитать количество едениц и записывать в массив. Вернуть этот массив.