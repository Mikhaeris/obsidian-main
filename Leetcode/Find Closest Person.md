**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
	int findClosest(int x, int y, int z) {
		int dxz = abs(x-z);
		int dyz = abs(y-z);
		if (dxz < dyz) return 1;
		if (dxz > dyz) return 2;
		return 0;
	}
};
```
**Explanation:**
	Цель: На прямой линии(от 1 до 100) есть три человека. Два идут навстречу третьему. Тертий стоит на месте. Определить кто придет первее или они придут вместе.
	Решение: По модулю взять расстояние между 1 и 3, 2 и 3. И определить кто придет быстрее.