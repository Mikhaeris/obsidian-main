**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int numberOfPoints(vector<vector<int>>& nums) {
        int park[100] = {0};

        for (const auto& pr : nums) {
            for (int i = pr[0]; i <= pr[1]; ++i) {
                ++park[i-1];
            }
        }

        int ans = 0;
        for (const auto& c : park) {
            if (c) {
                ++ans;
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дана числовая прямая, где на некоторые промежутки заняты. Нужно найти сколько точеку на этой прямой занято.
	Pешение: Проходится по всем промежуткам и помечать, что там занято. Дальше пройтись по всей числовой прямой и посчитать сколько занято.