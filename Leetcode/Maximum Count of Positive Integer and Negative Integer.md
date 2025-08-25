**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximumCount(vector<int>& nums) {  
	    int count_zeroes = 0, count_positive = 0;  
	    for (int i = 0; i < nums.size(); i++) {  
	        if (nums[i] == 0) {  
	            count_zeroes++;  
	        }  
	        else if (nums[i] > 0) {  
	            count_positive++;  
	        }  
	    }  
	    int count_negative = nums.size() - count_zeroes - count_positive,;  
	    return max(count_negative, count_positive);  
	}
};
```
**Explanation:**
	Цель: Нужно посчитать количество отрицательных и положительных числе и вернуть макимальное.
	Решение: Посчитать негативные и положительные и вернуть максимальное.
