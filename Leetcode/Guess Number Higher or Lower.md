**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int guessNumber(int n) {
		int left = 0, right = n;
		while (left <= right) {
			int mid = left + (right - left) / 2;
			int ans = guess(mid);
			if (ans == -1) {
				right = mid - 1;
			} else if (ans == 1) {
				left = mid + 1;
			} else {
				return mid;
			}
		}
		  
		return -1;
	}
};
```
**Explanation:**
	Цель: Угадать число, которое загадано.
	Решение: Обычный алгоритм бинирного поиска.