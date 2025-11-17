**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool kLengthApart(vector<int>& nums, int k) {
        int dist = k;
        for (const auto& n : nums) {
            if (n == 1) {
                if (dist < k) {
                    return false;
                }
                dist = 0;
            } else {
                ++dist;
            }
        }
        return true;
    }
};
```
**Explanation:**
	Цель: Дан массив нулей и едениц. Нужно проверить, что каждая еденица находится на расстоянии k между всеми другими еденицами.
	Решение: Пропустить первую еденицу, дальше проверять что каждая селдуюущая еденица находится на расстоянии k между предыдущей(т.е. производить подсчет нулей и каждый раз при встрече еденицы сбрасывать счетчик).