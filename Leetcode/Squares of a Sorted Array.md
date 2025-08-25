**Complexity:** Easy
Answer1:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> sortedSquares(vector<int>& nums) {
		for (int i = 0; i < nums.size(); ++i) {
			nums[i] *= nums[i];
		}
		sort(nums.begin(), nums.end());
		return nums;
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно возвести каждый элемент в квадрат и вернуть отсортированный массив.
	Решение: Возвести каждый элемент в квадрат и отсортировать.

Answer2:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	vector<int> sortedSquares(vector<int>& nums) {
		vector<int> ans(nums.size());
		  
		int l = 0, r = nums.size()-1;
		for (int i = ans.size()-1; i >= 0; --i) {
			if (abs(nums[l]) > abs(nums[r])) {
				ans[i] = nums[l] * nums[l];
				++l;
			}
			else {
				ans[i] = nums[r] * nums[r];
				--r;
			}
		}
		  
		return ans;
	}
};
```
**Explanation:**
	Цель: Дан массив, нужно возвести каждый элемент в квадрат и вернуть отсортированный массив.
	Решение: В конечном массиве будут содержаться только положительные элементы, значит знак не важен.
	Создать новый пустой массив. Начать заполнять с конца. Два указателя, один на начало данного массива, второй на конец. Сравнивать два числа и какое по модулю больше, то и возводить в квадрат и впихивать в новый массив.