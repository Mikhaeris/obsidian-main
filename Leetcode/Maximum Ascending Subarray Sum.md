**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maxAscendingSum(vector<int>& nums) {  
	    int max_sum = 0; int sum = nums[0];  
	    for (int i = 1; i < nums.size(); ++i) {  
	        if (nums[i] > nums[i-1]) {  
	            sum += nums[i];  
	        }  
	        else {  
	            max_sum = max(max_sum, sum);  
	            sum = nums[i];  
	        }  
	    }  
	    return max(max_sum, sum);  
	}
};
```
**Explanation:**
	Цель: Найти максимальную возврастающую последовательность по сумме элементов.
	Решение: Если элемент больше предыдущего, то прибавлять к сумме. Если нет, то начинать последовательность заново, sum равняется этому элементу, и обновить максимальную сумму. В конце вернуть максимум между максимальной суммой и текущей.
