**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(?)
Code:
Solution:
```cpp
class Solution {
public:
	void get_nums(vector<int>& nums, string& version) {
	    string temp;
	
	    bool n = true;
	    for (int i = 0; i <= version.length(); ++i) {
	        while (n && version[i] == '0' && i < version.length()) {
	            ++i;
	        }
	        
	        if (version[i] == '.' || version[i] == '\0') {
	            if (temp.length() == 0) {
	                temp += '0';
	            }
	            nums.push_back(stoi(temp));
	            temp = "";
	            n = true;
	            continue;
	        }
	
	        temp += version[i];
	        n = false;
	    }
	}

	int compareVersion(string version1, string version2) {
	    vector<int> nums1;
	    vector<int> nums2;
	    get_nums(nums1, version1);
	    get_nums(nums2, version2);
	    
	    if (nums1.size() != nums2.size()) {
	        while (nums1.size() < nums2.size()) {
	            nums1.push_back(0);
	        }
	        while (nums1.size() > nums2.size()) {
	            nums2.push_back(0);
	        }
	    }
	
	    for (int i = 0; i < nums1.size(); ++i) {
	        if (nums1[i] < nums2[i]) {
	            return -1;
	        }
	
	        if (nums1[i] > nums2[i]) {
	            return 1;
	        }
	    }
	
	    return 0;
	}
};
```
**Explanation:**
	Цель: Даны две строки, в которых через точки стоят числа, нужно сравнить эти числа. Если строки не равны, то меньшая дополняется нулями.
	Pешение: Расспарсить числа в массив, дополнить нулями меньший массив. Сранвить каждый элемент в массиве.