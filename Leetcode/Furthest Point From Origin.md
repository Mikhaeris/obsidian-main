**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int furthestDistanceFromOrigin(string moves) {
        int l = 0, r = 0, s = 0;
        for (const auto& move : moves) {
            if (move == 'L') ++l;
            if (move == 'R') ++r;
            if (move == '_') ++s;
        }

        int ans = 0;
        if (l > r) {
            ans = l + s - r;
        } else if (r > l) {
            ans = r + s - l;
        } else {
            ans = l + s - r;
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: В начале точка находит в 0 координате, нужено определить максимальное расстояние, окторая она модет пройти. Дана последовательность символов: L - движение влево, R - движение вправо, \_ - движение в любом направление.
	Pешение: Посчиать все L, R, \_, найти чего больше всего, туда и нужно идти, переернув все \_ в это направление. Не забыв вычесть другое направление.