**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int removeDuplicates(vector<int>& nums, int i = 1) {  
	    for (int j = 0; j < nums.size(); j++) {  
	        if (nums[j] != nums[i-1]) {  
	            nums[i++] = nums[j];  
	        }  
	    }  
	    return i;  
	}
};
```
**Explanation:**
	Цель: Удалить все дупликаты в отсортированном массиве.
	Решение: Два указателя. Один указывает на текущую неповторяющююся позицию. Другой на новое число.