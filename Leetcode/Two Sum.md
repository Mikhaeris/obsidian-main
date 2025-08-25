**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int, int> map_nums;
  
        for (int i = 0; i < nums.size(); i++) {
            if (map_nums.find(target - nums[i]) != map_nums.end()) {
                return { map_nums[target - nums[i]], i };
            }
            map_nums[nums[i]] = i;
        }
  
        return {};
    }
};
```
**Explanation:**
	Цель: Найти два элемента в массиве, сумма которых равна target.
	Решение: Хэш табица, в которой ключ - значение индекс.
	Проходится по каждому элементу массива, если из target вычесть этот элемент и если он есть в хэш таблице, то вернуть индекс элемента из хэш таблицы и индекс этого элемента. Иначе добавить элемент и его индекс в хэш таблицу.