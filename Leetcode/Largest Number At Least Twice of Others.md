**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int dominantIndex(vector<int>& nums) {
		int fm = 0, ind = 0, sm = 0;
		for (int i = 0; i < nums.size(); ++i) {
			if (nums[i] > fm) {
				sm = fm;
				fm = nums[i];
				ind = i;
			} else if (nums[i] > sm) {
				sm = nums[i];
			}
		}
		  
		if (sm*2 <= fm) {
			return ind;
		}
		  
		return -1;
	}
};
```
**Explanation:**
	Цель: Нужно узнать индекс максимлаьного числа, если это число больше любого числа в массиве как миним в два раза.
	Решение: Искать максимальное и второе максимально число. Проходится по массиву и искать такие числа, так же запоминая индекс максимального числа.
	Проверить, что второе максимальное число умноженное на два меньше максимального числа.