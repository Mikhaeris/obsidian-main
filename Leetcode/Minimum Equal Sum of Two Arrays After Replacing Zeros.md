**Complexity:** Medium
**Task En:**
	You are given two arrays `nums1` and `nums2` consisting of positive integers.
	You have to replace **all** the `0`'s in both arrays with **strictly** positive integers such that the sum of elements of both arrays becomes **equal**.
	Return _the **minimum** equal sum you can obtain, or_ `-1` _if it is impossible_.
**Task Ru:** 
	Вам даны два массива `nums1` и `nums2`, состоящие из положительных целых чисел.
	Вы должны заменить все `0` в обоих массивах на строго положительные целые числа так, чтобы суммы элементов обоих массивов стали равны.
	Верните **минимально возможную общую сумму**, которую можно получить, или `-1`, если это невозможно.

**Example:**
	**Example 1:**
		**Input:** nums1 = [3,2,0,1,0], nums2 = [6,5,0]
		**Output:** 12
		**Explanation:**
		We can replace 0's in the following way:
		Replace the two 0's in nums1 with the values 2 and 4. The resulting array is nums1 = [3,2,2,1,4].
		Replace the 0 in nums2 with the value 1. The resulting array is nums2 = [6,5,1].
		Both arrays have an equal sum of 12. It can be shown that it is the minimum sum we can obtain.
	**Example 2:**
		**Input:** nums1 = [2,0,2,0], nums2 = [1,4]
		**Output:**  -1
		**Explanation:**
			It is impossible to make the sum of both arrays equal.
**Constraints:**
	`1 <= nums1.length, nums2.length <= 105`
	`0 <= nums1[i], nums2[i] <= 106`
	
**Answer:**
	Resources:
		Time Complexity: O(n + m)
		Space Complexity: O(1)
Code:
```cpp
class Solution {
public:
	long long minSum(vector<int>& nums1, vector<int>& nums2) {
        long long minSum1 = 0, minSum2 = 0;
        int countZero1 = 0, countZero2 = 0;
        for (int& num : nums1) {
	        minSum1 += num;
            if (num == 0)
                countZero1++;     
        }
        
        for (int& num : nums2) {
	        minSum2 += num;
            if (num == 0)
                countZero2++;
        }
        
		minSum1 += countZero1;
		minSum2 += countZero2;
		
        if (minSum1 == minSum2)
            return minSum1;
        else if (minSum1 > minSum2)
            return (countZero2 > 0) ? minSum1 : -1;
        else
            return (countZero1 > 0) ? minSum2 : -1;
    }
};
```

**Explanation:**
	Цель: Вернуть минимальную возможную общую сумму
	Решение: Для начала нужно посчитать минимальную сумму чисел для каждого массива, так же посчитать количество нулей, дальше прибавить к минимальной сумме количество нулей.
	Теперь важно знать лишь одно - есть ли нули в массиве.
	Можно просто проверить если минмальная сумма первого массива больше второй, то проверить, есть ли во втором массиве нули, если есть то вернуть минимальную сумма первого массива. И такую же обратную проверку наоброт.