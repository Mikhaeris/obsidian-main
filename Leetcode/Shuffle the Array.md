**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> shuffle(vector<int>& nums, int n) {
        vector<int> vec(n*2);

        int l = 0, r = n;
        for (int i = 0; i < n*2; ++i) {
            vec[i] = (i & 1) ? nums[r++] : nums[l++];
        }

        return vec;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно его перемешать, что первый элемент равен первому, второй равен элементу по середине и так далее.
	Pешение: Два указателя, вставлять элементы на свои позиции. Вернуть массив.