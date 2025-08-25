**Complexity:** Easy
**Task En:**
	Given a **zero-based permutation** `nums` (**0-indexed**), build an array `ans` of the **same length** where `ans[i] = nums[nums[i]]` for each `0 <= i < nums.length` and return it.
	A **zero-based permutation** `nums` is an array of **distinct** integers from `0` to `nums.length - 1` (**inclusive**).
**Task Ru:** 
	Дан нулевой (с нуля) массив-перестановка `nums` (индексация начинается с 0). Постройте массив `ans` такой же длины, где для каждого индекса `i` в диапазоне от `0` до `nums.length - 1` выполняется: **`ans[i] = nums[nums[i]]`** и верните этот массив.
	**Нулевая перестановка `nums`** — это массив, состоящий из различных целых чисел от `0` до `nums.length - 1` включительно.

**Example:**
	**Example 1:**
		**Input:** nums = [0,2,1,5,3,4]
		**Output:** [0,1,2,4,5,3]
		**Explanation:**
		The array ans is built as follows: 
		ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
	    = [nums[0], nums[2], nums[1], nums[5], nums[3], nums[4]]
	    = [0,1,2,4,5,3]
	**Example 2:**
		**Input:** nums = [5,0,1,2,3,4]
		**Output:** [4,5,0,1,2,3]
		**Explanation:** The array ans is built as follows:
		ans = [nums[nums[0]], nums[nums[1]], nums[nums[2]], nums[nums[3]], nums[nums[4]], nums[nums[5]]]
	    = [nums[5], nums[0], nums[1], nums[2], nums[3], nums[4]]
	    = [4,5,0,1,2,3]
**Constraints:**
	`1 <= nums.length <= 1000`
	`0 <= nums[i] < nums.length`
	The elements in `nums` are **distinct**.
	
**Answer:**
	Resources:
		Time Complexity: O(n)
		Space Complexity: O(n)
Code:
```cpp
class Solution {
public:
    vector<int> buildArray(vector<int>& nums) {
        int size = nums.size();
        vector<int> ans(size, 0);
        for (int i = 0; i < size; i++)
            ans[i] = (nums[nums[i]]);
        return ans;
    }
};
```

**Explanation:**
	Цель: ans[i] = nums[nums[i]]
	Решение: Просто пройтись по каждому элеенту и занести его в новый массив и вернуть его.