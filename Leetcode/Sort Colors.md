**Complexity:** Medium
**Task:**
	En: Given an array `nums` with `n` objects colored red, white, or blue, sort them **[in-place](https://en.wikipedia.org/wiki/In-place_algorithm)** so that objects of the same color are adjacent, with the colors in the order red, white, and blue.
	We will use the integers `0`, `1`, and `2` to represent the color red, white, and blue, respectively.
	You must solve this problem without using the library's sort function.
	Ru: Дан массив `nums` из `n` объектов, окрашенных в красный, белый или синий цвет. Отсортируйте его _на месте_ так, чтобы объекты одного цвета стояли рядом, в порядке: красный, белый, синий.
	Мы будем использовать целые числа `0`, `1` и `2` для представления цветов: красного, белого и синего соответственно.
	Вы должны решить эту задачу **без использования** встроенной функции сортировки из библиотеки.
	
**Example:**
	**Example 1:**
		**Input:** nums = [2,0,2,1,1,0]
		**Output:** [0,0,1,1,2,2]
	**Example 2:**
		**Input:** nums = [2,0,1]
		**Output:** [0,1,2]

**Constraints:**
	`n == nums.length`
	`1 <= n <= 300`
	`nums[i]` is either `0`, `1`, or `2`.
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution 1:
```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int size_vec = nums.size(), r_ptr = size_vec;
        for (int i = 0; i < r_ptr; i++) {
            if (nums[i] < 1) {
                nums.insert(nums.begin(), nums[i]);
                nums.erase(nums.begin()+i+1);
            }
            else if (nums[i] > 1) {
                nums.insert(nums.end(), nums[i]);
                nums.erase(nums.begin() + i);
                i--;
                r_ptr--;
            }
        }
    }
};
```
Solution 2:
```cpp
class Solution {
public:
    void sortColors(vector<int>& nums) {
        int zero = 0, one = 0, two = 0;
        for (int i = 0; i < nums.size(); ++i) {
            if (nums[i] == 0) {
                ++zero;
            }
            else if (nums[i] == 1) {
                ++one;
            }
            else if (nums[i] == 2) {
                ++two;
            }
        }
        for (int i = 0; i < zero; ++i) {
            nums[i] = 0;
        }
        for (int i = zero; i < zero+one; ++i) {
            nums[i] = 1;
        }
        for (int i = zero + one; i < zero + one + two; ++i) {
            nums[i] = 2;
        }
    }
};
```
**Explanation:**
	Цель: Просто отсортировать массив, но в массиве содержаться только три числа: 0, 1, 2.
	Решение 1: Проходится по каждому числу,
		если цифра меньше еденицы, отправлять вперед массива
		если цифра больше еденицы, отправать в конец массива
	Решение 2: Посчитать количество нулей, едениц, двоек. И перезаписать массив в отсортированном виде.
	Примечание: все операции должны проводится на данном массива.