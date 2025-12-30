**Complexity:** Easy
Answer:
	Time Complexity: O(N^2)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countKDifference(vector<int>& nums, int k) {
        int count = 0;
        for (int i = 0; i < nums.size()-1; ++i) {
            for (int j = i+1; j < nums.size(); ++j) {
                if (abs(nums[i] - nums[j]) == k) {
                    ++count;
                }
            }
        }
        return count;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно посчитать в нем количество таких пар, разница которых по модулю равнается числу k.
	Pешение: Проходится по всем элементам от текущего и искать подходящие, переодить к следующему элементу, так пока не закончится массив.
