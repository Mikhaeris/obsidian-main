**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

int main() {
    int a, b, c;
    cin >> a >> b >> c;

    int min_count = a/1;
    min_count = min(min_count, b/2);
    min_count = min(min_count, c/4);

    cout << ((min_count * 1) + (min_count * 2) + (min_count * 4)) << endl;

    return 0;
}
```
**Explanation:**
	Цель: Даны три фрукта в компот можно добавлять в соотношении 1:2:4. Узнать сколько всего фруктов будет в компоте.
	Решение: Узнать минимальное количество фрукта, которое можно положить и умножить на соотношение каждого фрукта.