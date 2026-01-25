**Complexity:** Easy
Answer:
	Time Complexity: O(N\*log(N)\*N)
	Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
    int minimumDifference(vector<int>& nums, int k) {
        sort(nums.begin(),  nums.end());
        int ans = nums[k-1] - nums[0];
        for (int i = k - 1; i < nums.size(); ++i) {
            ans = min(ans, nums[i] - nums[i - k + 1]);
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Нужно выбрать любых k студентов и получить минмиальную разницу между максимальным и минимальным.
	Pешение: Задача на [[Sliding window]]. Для начала следует отсортировать, так получится выбрать лучшее k студентов для получения минимальной разницы. Проходится по всем в виде окна и искать минимальную разницу между первым и последним студентом в окне.