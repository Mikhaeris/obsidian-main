**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int addedInteger(vector<int>& nums1, vector<int>& nums2) {
        int n = nums1.size();
        int max1 = 0, max2 = 0;
        for (int i = 0; i < n; ++i) {
            max1 = max(max1, nums1[i]);
            max2 = max(max2, nums2[i]);
        }

        return max2 - max1;
    }
};
```
**Explanation:**
	Цель:  Дано два массива, к массиву один добавили какое-то число и получился массив два. Нужно узнать какое это число было.
	Решение: Найти в какждом массиве максимальное(или минимальное) число и из второго макимального вычесть первое максимальное.