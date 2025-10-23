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
    int sum1 = 0, sum2 = 0;
    for (int i = 0; i < 3; ++i) {
        int num; cin >> num;
        sum1 += num;
    }
    for (int i = 0; i < 3; ++i) {
        int num; cin >> num;
        sum2 += num;
    }

    int n; cin >> n;

    int count1 = 0;
    if (sum1 > 5) {
        count1 = (sum1 / 5);
        sum1 -= count1 * 5;
    }
    count1 += (sum1 > 0) ? 1 : 0;

    int count2 = 0;
    if (sum2 > 10) {
        count2 = (sum2 / 10);
        sum2 -= count2 * 10;
    }
    count2 += (sum2 > 0) ? 1 : 0;

    if (count1 + count2 <= n) {
        cout << "YES" << '\n';
    } else {
        cout << "NO" << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Даны кубики и медали, нужно разложить их по полкам, но на полку можно разложить только 5 кубков и 10 медалей. Узнать получится ли их разложить.
	Решение: Просто проверить.