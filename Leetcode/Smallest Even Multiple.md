**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int smallestEvenMultiple(int n) {
        return (n & 1) ? n*2 : n;
    }
};
```
**Explanation:**
	Цель: Найти минимальное число, которое делитс на само себя и на 2.
	Решение: Если чсило делится на 2, то вернуть его, иначе вернуть число умноженное на 2.