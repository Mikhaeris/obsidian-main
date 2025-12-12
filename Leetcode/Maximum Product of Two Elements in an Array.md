**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxProduct(vector<int>& nums) {
        int m1 = 0, m2 = 0;
        for (const auto& num : nums) {
            if (num >= m1) {
                m2 = m1;
                m1 = num;
            } else if (num >= m2) {
                m2 = num;
            }
        }
        return (m1-1)*(m2-1);
    }
};
```
**Explanation:**
	Цель: Дан массив. Нужно найти два максимальных числа и вернуть их произведение, при этом вычесть из каждого один.
	Pешение: Найти два максимальных числа, вычесть по еденичке и перемножить.