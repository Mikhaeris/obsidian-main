**Complexity:** Easy  
Answer:  
- Time Complexity: O(N)
- Space Complexity: O(1)

Code:  
```cpp
class Solution {
public:
    int minimumCost(vector<int>& nums) {
        int m1 = nums[0], m2 = INT_MAX, m3 = INT_MAX;
        for (int i = 1; i < nums.size(); ++i) {
            if (m2 > nums[i]) {
                m3 = m2;
                m2 = nums[i];
            } else if (m3 > nums[i]) {
                m3 = nums[i];
            }
        }
        return m1 + m2 + m3;
    }
};
```
**Explanation:**
- Цель: Дан массив. Нужно разделить его на три непересекающихся подмассива. Чтобы их стоимость была минимальной. Под стоимостью понимается первый элемент в подмассиве.
- Pешение: Для начала первый подмассив всегда будет начинаться с первого элемента. Далее просто нужно найти два минимальных числа в массиве и вернуть сумму трех чисел.