**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int totalMoney(int n) {
        int ans = 0, t = 1;
        for (int i = 1; i <= n; ++i) {
            ans += t++;
            if (i % 7 == 0) {
                t -=6;
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Кажый день откладывается на одну онету больше, каждый новый понедельник на одну больше чем в прошлый.
	Решение: каждый понедельник сбрасывать уменьшать счетчик на 6.