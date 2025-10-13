**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>

using namespace std;

using ull = unsigned long long;

int main() {
    ull count = 0;
    ull  n, x; cin >> n >> x;
    while (n--) {
        char ch; cin >> ch;
        ull num; cin >> num;

        if (ch == '+') {
            x += num;
        } else if (ch == '-') {
            (x >= num)
            ? x -= num
            : ++count;
        }
    }
    cout << x << ' ' << count << endl;
    return 0;
}
```
**Explanation:**
	Цель: Раздают мороженное. Если + значит только мороженного добавляется, если минус значит столько мороженного отнимается, если мороженного не хватает ребенок уходит расстроенный. Узнать сколько мороженного останется в конце и столько детей будет растроенно.
	Решение: Итеративно выыполнять все по шагам. В конце вывести результат.