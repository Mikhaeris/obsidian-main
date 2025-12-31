**Complexity:** Easy
Answer:
	Time Complexity: O(1)
	Space Complexity: O(1)
Code:
Solution:
```cpp
class Solution {
public:
    int passThePillow(int n, int time) {
        int count = time / (n - 1);
        int extra = time % (n - 1);
        return (count % 2 == 0) ? extra + 1 : n - extra;
    }
};
```
**Explanation:**
	Цель: Дано количество человек и время. За одну секунду один человек передает подушку другому человеку. Когда доходит до последнего, то передают в обратном порядке. Нужно узнать у кого будет подушка через жанное время.
	Pешение: Найти сколько полных циклов и остаток. Если количество полных циклов четное, то остоток плюс один, иначе в обратном порядке это количество минус остаток.
