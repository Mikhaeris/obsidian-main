**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int getCommon(vector<int>& nums1, vector<int>& nums2) {
        int f = 0, s = 0;
        while (f < nums1.size() && s < nums2.size()) {
            if (nums1[f] == nums2[s]) {
                return nums1[f];
            }

            if (nums1[f] < nums2[s]) {
                ++f;
            } else {
                ++s;
            }
        }
        return -1;
    }
};
```
**Explanation:**
	Цель: Даны два отсортированных массива чисел. Нужно найти число, которое содержится в обоих и при этом является наименьшим.
	Pешение: Два указателя, один по первому, второй по второму массиву. Если числа равны, то вернуть текущее число, если первое меньше второго, то двигать первый указатель вперед, иначе двигать второй.
