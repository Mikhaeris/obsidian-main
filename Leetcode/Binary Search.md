**Complexity:** Easy
Answer:
	Time Complexity: O(logN)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int search(vector<int>& nums, int target) {  
	    int l = 0, r = nums.size()-1;  
	    while (l < r) {  
	        int mid = (r+l)/2;  
	        if (target <= nums[mid]) {  
	            r = mid;  
	        } else {  
	            l = mid+1;  
	        }  
	    }  
	  
	    if (nums[l] != target) {  
	        return -1;  
	    }  
	  
	    return l;  
	}
};
```
**Explanation:**
	Цель: Реализовать алгоритм бинарного поиска.
	Решение: Простой алгоритм бинарного поиска. Три указателя: левая граница, правая граница, центр(между левым и правым).
	Сравниваем число с центором и в зависимости от этого сдвигаем левую или правую границу.