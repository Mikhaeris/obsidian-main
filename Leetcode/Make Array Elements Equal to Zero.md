**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int countValidSelections(vector<int>& nums) {
        int sum_l = 0, sum_r = 0;
        for (const auto& num : nums) {
            sum_r += num;
        }

        int count = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] == 0) {
                if (sum_l == sum_r) {
                    count += 2;
                } else if (sum_l == sum_r-1) {
                    count += 1;
                } else if (sum_l-1 == sum_r) {
                    count += 1;
                }
            } else {
                sum_l += nums[i];
                sum_r -= nums[i];
            }
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Пинг понг в одномернном массиве. Нужно узнать сколько есть выигрышных позиций(вариантов).
	Решение: Посчитать всю сумму массива. Дальше считать сумму слева, убавляю сумму справа, если текущий эемент равен нул., то проверять возможные варианты(слева и справа равны - значит добавить 2, слева на один меньше - добавить 1, справа на один меньше добавить 1). Вернуть все возможные варианты для выигрыша.