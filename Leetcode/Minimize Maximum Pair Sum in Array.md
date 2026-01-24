**Complexity:** Medium
Answer:
	Time Complexity: O(N\*log(N)\*N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int minPairSum(vector<int>& nums) {
        sort(nums.begin(), nums.end());

        int l = 0, r = nums.size()-1;
        int max_pr = 0;
        while (l < r) {
            max_pr = max(max_pr, nums[l] + nums[r]);
            ++l;
            --r;
        }

        return max_pr;
    }
};
```
**Explanation:**
	Цель: Минимализировать максимальную сумму пар чисел.
	Pешение: Самый лучший варинат сопостовлять максимальное число с минимальным чиилом. Так что можно отсортировтаь массив и искать в нем максимальную пару, сопоставляя максимальное с минимальным, пока пары чисел не закончаться. Вернуть максимальную пару.