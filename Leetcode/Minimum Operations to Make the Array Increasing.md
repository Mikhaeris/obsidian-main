**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minOperations(vector<int>& nums) {
        int n = nums.size();
        int count = 0;
        for (int i = 1; i < n; ++i) {
            if (nums[i] <= nums[i-1]) {
                int diff = nums[i-1] - nums[i];
                nums[i] += diff + 1;
                count += diff + 1;
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно сделать его строго возврастающим за минимальное количество шагов.
	Pешение: Если следующий элемент меньше или равняетя текущему, то нужно найти разность между двумя элементами и прибавить один, параллельно считать сколько операций производится.