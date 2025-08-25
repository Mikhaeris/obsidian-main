**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
class Solution {
public:
    vector<int> transformArray(vector<int>& nums) {
        vector<int> ans(nums.size());

        int l = 0, r = nums.size()-1;
        for (const auto& num : nums) {
            if (num % 2) {
                ans[r--] = 1;
            } else {
                ans[l++] = 0;
            }
        }

        return ans;
    }
};
```
**Explanation:**
	Цель: Дан массив, нужно все четные числа превратить в 0, а нечетные в 1 и отсортировать массив.
	Решение: Создать новый массив, где будут сохраняться 0 и 1. Проходится по данному массиву и заполнять 0 слева, а 1 справа.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution1:
```cpp
class Solution {
public:
	vector<int> transformArray(vector<int>& nums) {
		int count = 0;
		for (const int& num : nums) {
			count += !(num & 1);
		}
		  
		for (int& num : nums) {
			num = (count-- > 0) ? 0 : 1;
		}
		  
		return move(nums);
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно все четные числа превратить в 0, а нечетные в 1 и отсортировать массив.
	Решение: Посчитать количество нулей. Заполнить данный массив 0 и 1.

Solution2:
```cpp
class Solution {
public:
	vector<int> transformArray(vector<int>& nums) {
		int count = 0;
		for (const int& num : nums) {
			count += !(num & 1);
		}
		
		for (int i = 0; i < count; ++i) {
			nums[i] = 0;
		}
		  
		for (int i = count; i < nums.size(); ++i) {
			nums[i] = 1;
		}
		  
		return move(nums);
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно все четные числа превратить в 0, а нечетные в 1 и отсортировать массив.
	Решение: Посчитать количество нулей. Заполнить данный массив 0 и 1.