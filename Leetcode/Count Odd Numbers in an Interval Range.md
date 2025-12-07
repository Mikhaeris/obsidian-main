**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countOdds(int low, int high) {
        int res = (high - low) / 2;
        if (low % 2 == 1 || high % 2 == 1) {
            ++res;
        }
        return res;
    }
};
```
**Explanation:**
	Цель: Дан промежуток между двумя числами. Нужнго ущзнать сколько нечетных чисел содержится в этом промежутке.
	Pешение: Четные и нечетные числа чередуются. Следовательно нужно просто узнать сколько чисел в промежутке и подеить на два. Если один из концов нечетный, то к ответу прибавить один.