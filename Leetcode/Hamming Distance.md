**Complexity:** Easy
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int hammingDistance(int x, int y) {
        int z = x ^ y;
        
        int count = 0;
        while (z) {
            z &= z-1;
            count++;
        }

        return count;
    }
};
```
**Explanation:**
	Цель: Расстояние Хэмингвейя - это число, которое показывает различие в битах между двумя числами. Узнать расстояние Хэмингвейя между двумя числами.
	Pешение: XOR между двумя числами и с помощью алгоритма Кернигана подсчитать количество битов в числе.