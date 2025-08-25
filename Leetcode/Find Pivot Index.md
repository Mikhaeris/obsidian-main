**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int pivotIndex(vector<int>& nums) {
        int left_summ = 0, right_summ = 0;
        for (int i = 1; i < nums.size(); ++i) {
            right_summ += nums[i];
        }
        if (left_summ == right_summ) {
            return 0;
        }
  
        for (int i = 1; i < nums.size(); ++i) {
  
            left_summ += nums[i-1];
            right_summ -= nums[i];
  
            if (left_summ == right_summ) {
                return i;
            }
        }
  
        return -1;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно найти такой левый индекс, где элементы слва будут равны элементам справа.
	Решение: Посчитать сумму элеменгтов начиная с первого индекса.
	Дальше проходится по индескам, добавляя для левой суммы левый элемент от индекса и убавлять правый жлемент от индекса.