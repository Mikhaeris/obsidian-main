**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
```cpp
class Solution {
public:
    vector<int> minBitwiseArray(vector<int>& nums) {
        size_t n = nums.size();
        vector<int> ans(n, -1);
        for (size_t i = 0; i < n; ++i) {
            if (nums[i] % 2 != 0) {
                auto z = ((nums[i] + 1) & ~nums[i]) >> 1;
                ans[i] = (nums[i] & ~z);
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Даны два отсортированных линкед листа. Нужно их объеденить.
	Pешение: Довольно хитрый трюк. Можно догадаться что числа отличаются жруг оот друга только один битом(конкртено первый завершающих едениц) требуется его перевернуть. Поэтому в z это и происходит. Конекртено этот бит не получится найти, но можно найти следующий за ним бит он будет равен (n + 1) & (~n) (от трюка (~n & n) для нахождения самого правого включенного бита)