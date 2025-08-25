**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int maximumProduct(vector<int>& nums) {
	    int amax[3] = {INT_MIN, INT_MIN, INT_MIN};
	    int amin[2] = {INT_MAX, INT_MAX};
	    for (const int& num : nums) {
	        if (num < amin[1]) {
	            amin[0] = amin[1];
	            amin[1] = num;
	        } else if (num < amin[0]) {
	            amin[0] = num;
	        }
	
	        if (num > amax[2]) {
	            amax[0] = amax[1];
	            amax[1] = amax[2];
	            amax[2] = num;
	        } else if (num > amax[1]) {
	            amax[0] = amax[1];
	            amax[1] = num;
	        } else if (num > amax[0]) {
	            amax[0] = num;
	        }
	    }
	
	    int fmax = amin[0] * amin[1] * amax[2],
	        smax = amax[0] * amax[1] * amax[2];
	
	    return (fmax > smax) ? fmax : smax;
	}
};
```
**Explanation:**
	Цель: Дан массив цисел, нужно найти три таких числа, которые дадут максимальное произведене.
	Решение: Найти три максимальных и два минимальных числа(потому что - * - = +, а - * - * - = -). Вернуть максимальное произведение из: два минимаьных и одно максимаьное или три максимальных.