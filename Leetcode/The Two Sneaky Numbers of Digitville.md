**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution1:
```cpp
class Solution {
public:
    vector<int> getSneakyNumbers(vector<int>& nums) {
        vector<int> ans;
        unordered_map<int, int> mp;
        for (const auto& num : nums) {
            if (++mp[num] > 1) {
                ans.push_back(num);
            }
        }
        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно найти два таких числа, котрые повторяются в массиве два раза.
	Решение: В хэш таблице хранить число и количество его повторений. Если количество повторений больше одного, то добавить в массив. Вернуть массив.
	P.S. Быстро работает на больших данных, но занимает намного больше места.

Answer:
	Time Complexity: O(N)
	Space Complexity: O(2)
Code:
Solution2:
```cpp
class Solution {
public:
    vector<int> getSneakyNumbers(vector<int>& nums) {
        sort(nums.begin(), nums.end());

        vector<int> ans;
        for (int i = 1; i < nums.size(); ++i) {
            if (nums[i-1] == nums[i]) {
                ans.push_back(nums[i]);
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив чисел. Нужно найти два таких числа, котрые повторяются в массиве два раза.
	Решение: Отсортировать массив. Проходится по массиву и искать соседние совпадающие элементы и добавлять в массив. Вернуть массив.
	P.S. Меньше памяти, но чуть медленее будет работать на больших даных.