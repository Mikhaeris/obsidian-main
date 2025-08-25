**Complexity:** Easy
**Task:**
	En: Given an integer array `nums`, return the number of subarray of length 3 such that the sum of the first and third numbers equals _exactly_ half of the second number.
	Ru: Дан массив целых чисел nums. Верните количество подмассивов длины 3, таких, что сумма первого и третьего чисел равна _ровно_ половине второго числа

**Example:**
	**Example 1:**
		**Input:** nums = [1,2,1,4,1]
		**Output:** 1
		**Explanation:**
		Only the subarray `[1,4,1]` contains exactly 3 elements where the sum of the first and third numbers equals half the middle number.
	**Example 2:**
		**Input:** nums = [1,1,1]
		**Output:** 0
		**Explanation:**
		`[1,1,1]` is the only subarray of length 3. However, its first and third numbers do not add to half the middle number.
**Constraints:**
	`3 <= nums.length <= 100`
	`-100 <= nums[i] <= 100`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int countSubarrays(vector<int>& nums, int countSubArrays = 0) {
        for (int i = 1; i < nums.size() - 1; ++i) {
            if ((nums[i - 1] + nums[i + 1]) * 2 == nums[i])
                ++countSubArrays;
        }
        return countSubArrays;
    }
};
```

**Explanation:**
	Проходится по трем ячейкам(по блокам из трех ячеек).
	Формула для проверки этого блока:
		**(Первая ячейка + третья ячейка) * 2* == вторая ячейка.**
	Считать количество таких ячеек, созраняя countSubArrays.
	Вернуть countSubArrays.