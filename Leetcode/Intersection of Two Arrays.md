**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> intersection(vector<int>& nums1, vector<int>& nums2) {  
	    set<int> s1(nums1.begin(), nums1.end());  
	    set<int> s2(nums2.begin(), nums2.end());  
	  
	    vector<int> result;  
	    for (int num : s1) {  
	        if (s2.find(num) != s2.end()) {  
	            result.push_back(num);  
	        }  
	    }  
	  
	    return result;  
	}
};
```
**Explanation:**
	Цель: Дано два массива, нужно вернуть массив, из элементов, которые встречаются во обоих массивах.
	Решение: Переделать массивы в сеты и потом сложить два сета.
	Вернуть массив.