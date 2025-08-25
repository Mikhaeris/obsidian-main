**Complexity:** Medium
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int maxOperations(vector<int>& nums, int k) {
        sort(nums.begin(), nums.end());
  
        int count_pairs = 0, temp_summ = 0;
        int left = 0, right = nums.size() - 1;
        while (left < right) {
            temp_summ = nums[left] + nums[right];
            if (temp_summ == k) {
                ++count_pairs;
                ++left;
                --right;
            }
            else if (temp_summ < k) {
                ++left;
            }
            else {
                --right;
            }
        }
  
        return count_pairs;
    }
};
```
**Explanation:**
	Цель: Посчитать сколько есть пар в массиве, который при сумме образуют число k.
	Решение: Отсортировать массив. Проходится с помощью двух указателей.
	Если сумма на двух указателях равна, то казатели двигат на встречу друг другу, количесвто пар увеличивать.
	Если данная сумма меньше числа k, то двигать левый указатель.
	Если данная сумма больше числа k, то двигать правый указатель.