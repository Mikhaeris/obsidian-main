**Complexity:** Medium
**Task:**
	En: You are given an integer array `nums` of length `n` and a 2D array `queries`, where `queries[i] = [li, ri]`.
	For each `queries[i]`:
	- Select a subset of indices within the range `[li, ri]` in `nums`.
	- Decrement the values at the selected indices by 1.
	A **Zero Array** is an array where all elements are equal to 0.
	Return `true` if it is _possible_ to transform `nums` into a **Zero Array** after processing all the queries sequentially, otherwise return `false`.
	Ru: Вам дан целочисленный массив `nums` длины `n` и двумерный массив `queries`, где `queries[i] = [lᵢ, rᵢ]`.
	Для каждого `queries[i]`:
	- Выбрать подмножество индексов в диапазоне `[lᵢ, rᵢ]` в `nums`.
	- Уменьшить значения в выбранных индексах на 1.
	Массив нулей — это массив, в котором все элементы равны 0.
	Верните `true`, если после последовательной обработки всех запросов возможно превратить `nums` в массив нулей, иначе верните `false`.
	
**Example:**
	**Example 1:**
		**Input:** nums = [1,0,1], queries = [ [0,2] ]
		**Output:** true
		**Explanation:**
		**For i = 0:**
		    Select the subset of indices as `[0, 2]` and decrement the values at these indices by 1.
		    The array will become `[0, 0, 0]`, which is a Zero Array.
	**Example 2:**
		**Input:** nums = [4,3,2,1], queries = [ [1,3],[0,2] ]
		**Output:** false
		**Explanation:**
		**For i = 0:**
		    Select the subset of indices as `[1, 2, 3]` and decrement the values at these indices by 1.
		    The array will become `[4, 2, 1, 0]`.
		**For i = 1:**
		    Select the subset of indices as `[0, 1, 2]` and decrement the values at these indices by 1.
		    The array will become `[3, 1, 0, 0]`, which is not a Zero Array.

**Constraints:**
	`1 <= nums.length <= 105`
	`0 <= nums[i] <= 105`
	`1 <= queries.length <= 105`
	`queries[i].length == 2`
	`0 <= li <= ri < nums.length`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    bool isZeroArray(vector<int>& nums, vector<vector<int>>& queries) {
        vector<int> queriesSumm(nums.size()+1);

        for (int i = 0; i < queries.size(); ++i) {
            ++queriesSumm[queries[i][0]];
            --queriesSumm[queries[i][1]+1];
        }

        int temp = 0;
        for (int i = 0; i < nums.size(); ++i) {
            temp += queriesSumm[i];
            if (nums[i] > temp) {
                return false;
            }
        }
        return true;
    }
};
```

**Explanation:**
	Цель: Дан массив чисел и массив массивов в котором содержится диапазон, это диапазон, в котором числа в первом массиве уменьшаются. Нужно проверить что после всех операций получится в первом массиве 0.
	Решение: Есть такая штука как разность массивов ([[Difference Array]]).
	Создать дополнительный массив diff в котором будем помечать диапазоны.
	Потом делать обратные операции с изначальным массивом. Создать переменную в которой хранится постепенно накапливающаяся сумма из diff, на каждом шаге проверять есть nums[i] > temp (т.е. если сумма в ячейке больше накапливающейся суммы, то нулевой массив не получается.)