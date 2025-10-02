**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    int sumOfUnique(vector<int>& nums) {
        unordered_map<int, int> mp;

        for (const auto& num : nums) {
            mp[num]++;
        }

        int sum = 0;
        for (const auto& pr : mp) {
            if (pr.second == 1) {
                sum += pr.first;
            }
        }

        return sum;
    }
};
```
**Explanation:**
	Цель: Дан массив из чисел. Нужно почитать сумму уникальных элементов.
	Pешение: Посчитать повторения элементов. Если элемент повторяется один раз, то дбавлять его в сумму.