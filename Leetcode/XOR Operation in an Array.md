**Complexity:** Medium
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int xorOperation(int n, int start) {
		int arr_xor = start;
		while (--n) {
			arr_xor ^= (start += 2);
		}
		return arr_xor;
	}
};
```
**Explanation:**
	Цель: Дано число от
	Решение: 