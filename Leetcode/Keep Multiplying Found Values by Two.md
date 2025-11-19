**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int findFinalValue(vector<int>& nums, int original) {
        while (located(nums, original)) {
            original *= 2;
        }
        return original;
    }
private:
    bool located(vector<int>& nums, int original) {
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] == original) {
                return true;
            }
        }
        return false;
    }
};
```
**Explanation:**
	Цель: Дан массив и число. Нужно узнать каким станет число после всех операций. Если это число есть в массиве, то умножит его на два, иначе вернуть это число.
	Решение: Проверять число пока оно есть в массиве и множать его на два. В конце вернуть это число.