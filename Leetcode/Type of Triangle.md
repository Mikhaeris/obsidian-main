**Complexity:** Easy
**Task:**
	En: You are given a **0-indexed** integer array `nums` of size `3` which can form the sides of a triangle.
	A triangle is called **equilateral** if it has all sides of equal length.
	A triangle is called **isosceles** if it has exactly two sides of equal length.
	A triangle is called **scalene** if all its sides are of different lengths.
	Return _a string representing_ _the type of triangle that can be formed_ _or_ `"none"` _if it **cannot** form a triangle._
	Ru: Вам дан 0-индексный целочисленный массив nums размера 3, который может образовать стороны треугольника.
    Треугольник называется равносторонним, если все его стороны имеют одинаковую длину.
    Треугольник называется равнобедренным, если ровно две стороны имеют одинаковую длину.
    Треугольник называется разносторонним, если все его стороны имеют разную длину.
	Верните строку, представляющую тип треугольника, который можно образовать, или "none", если треугольник образовать нельзя.

	
**Example:**
	**Example 1:**
		**Input:** nums = [3,3,3]
		**Output:** "equilateral"
		**Explanation:** Since all the sides are of equal length, therefore, it will form an equilateral triangle.
	**Example 2:**
		**Input:** nums = [3,4,5]
		**Output:** "scalene"
		**Explanation:** 
nums[0] + nums[1] = 3 + 4 = 7, which is greater than nums[2] = 5.
nums[0] + nums[2] = 3 + 5 = 8, which is greater than nums[1] = 4.
nums[1] + nums[2] = 4 + 5 = 9, which is greater than nums[0] = 3. 
Since the sum of the two sides is greater than the third side for all three cases, therefore, it can form a triangle.
As all the sides are of different lengths, it will form a scalene triangle.

**Constraints:**
	`nums.length == 3`
	`1 <= nums[i] <= 100`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    string triangleType(vector<int>& nums) {
		sort(nums.begin(), nums.end());
		if (nums[0] + nums[1] > nums[2]) {
			set<int> tempSet(nums.begin(), nums.end());
			if (tempSet.size() == 1) {
				return "equilateral";
			}
			else if (tempSet.size() == 2) {
				return "isosceles";
			}
			else {
				return "scalene";
			}
		}
		return "none";
	}
};
```
**Explanation:**
	Цель: Нужно проверить это треугольник и если это треугольник, то вернуть что это за треугольник
	Решение: Сначала отсортировтаь массив. Проверить является ли эти данные треугольником (сумма двух меньших строн, должна быть меньше большей строны).
	Записать все данные в сет(множество без повторений).
	Если в сете только одно число, то это равносторонний.
	Если в сете два числа, то это равнобедренный.
	Если в сете три числа, то это разносторонний.