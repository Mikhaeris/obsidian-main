**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	bool doesAliceWin(string s) {
		for (const auto& ch : s) {
			if (ch == 'a' || ch == 'e' || ch == 'i' || ch == 'o' || ch == 'u') {
				return true;
			}
		}
		
		return false;
	}
};
```
**Explanation:**
	Цель: Узнать может ли Алиса победить.
	Pешение: Просто проверить, есть ли в строке гласные.
