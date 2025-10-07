**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int minElement(vector<int>& nums) {
        int min_el = nums[0];
        for (auto& num : nums) {
            int curr = 0;
            do {
                curr += num % 10;
            } while (num /= 10);
            min_el = min(min_el, curr);
        }
        return min_el;
    }
};
```
**Explanation:**
	Цель: Найти число с минмиальной сумма цифр в массиве.
	Pешение: считать сумму цифр в каждом числе. Вернуть минимальную сумму цифр.