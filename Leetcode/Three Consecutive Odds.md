**Complexity:** Easy
**Task:**
	En: Given an integer array `arr`, return `true` if there are three consecutive odd numbers in the array. Otherwise, return `false`.
	Ru: Дан целочисленное массив `arr`. Вернуть `true`, если в массиве есть три подряд идущих нечетных числа. В противном случае вернуть `false`.
	
**Example:**
	**Example 1:**
		**Input:** arr = [2,6,4,1]
		**Output:** false
		**Explanation:**
		There are no three consecutive odds.
	**Example 2:**
		**Input:** arr = [1,2,34,3,4,5,7,23,12]
		**Output:** true
		**Explanation:**
		[5,7,23] are three consecutive odds.
**Constraints:**
	`1 <= arr.length <= 1000`
	`1 <= arr[i] <= 1000`
	
Answer:
	Time Complexity: O(n)
	Space Complexity: O(1)
Code:
Solution 1:
```cpp
class Solution {
public:
    bool threeConsecutiveOdds(vector<int>& arr) {
        int arrSize = arr.size();
        for (int i = 0; i < arrSize-2; ++i) {
            if (arr[i] & 1) {
                if (arr[i + 1] & 1 && arr[i + 2] & 1)
                    return true;
                else
                    ++i;
            }
        }
        return false;
    }
};
```
Solution 2:
```cpp
class Solution {
public:
    bool threeConsecutiveOdds(vector<int>& arr) {
        int consecutiveOdds = 0;
        for (int i = 0; i < arr.size(); i++) {
            if (arr[i] % 2 == 1)
                consecutiveOdds++;
            else
                consecutiveOdds = 0;
                
            if (consecutiveOdds == 3)
                return true;
        }
        return false;
    }
};
```
**Explanation:**
	Цель: Вернуть true, если в массиве есть три подряд идущие нечетные числа.
	Решение 1: Просто проверять, если три идущие числа подряд.
	Решение 2: Считать количество идущих подряд нечетных чисел. Если чисто четное, то обнулять счетчик. Если счетчик равен трем, значит вернуть true. Если такая последовательность не найдена вернуть false.