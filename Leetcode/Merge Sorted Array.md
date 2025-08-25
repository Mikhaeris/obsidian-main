**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	void merge(vector<int>& nums1, int m, vector<int>& nums2, int n) {  
	    if (n == 0) {  
	        return;  
	    }  
	  
	    vector<int> nums3(m+n);  
	  
	    int i = 0, l = 0, r = 0;  
	    for (; i < m+n && r < n; ++i) {  
	        if (nums1[l] < nums2[r] && nums1[l] != 0) {  
	            nums3[i] = nums1[l++];  
	        }  
	        else {  
	            nums3[i] = nums2[r++];  
	        }  
	    }  
	  
	    for (; i < m+n; ++i) {  
	        nums3[i] = nums1[l++];  
	    }  
	  
	    for (int i = 0; i < m+n; ++i) {  
	        nums1[i] = nums3[i];  
	    }  
	}
};
```
**Explanation:**
	Цель: Дано два массива, нужно их сложить и отсортировать внутри первого массива.
	Решение: Создать третий массив, складывать на i-ый индекс меньший элемент из двух массивов. Потом переписать все в первый массив.
	P.S. Можно решить примитивно, записать элементы второго массива в конец первого и отсортировать.