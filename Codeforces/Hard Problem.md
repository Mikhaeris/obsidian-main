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
    int t; cin >> t;
    while (t--) {
        int m, a, b, c;
        cin >> m >> a >> b >> c;
        
        long ans = 0;
        if (a > m) {
            ans += m;
            a -= m;
        } else {
            ans += a;
            if (c > (m - a)) {
                ans += (m - a);
                c -= m - a;
            } else {
                ans += c;
                c = 0;
            }
        }

        if (b > m) {
            ans += m;
            b -= m;
        } else {
            ans += b;
            if (c > (m - b)) {
                ans += (m - b);
                c -= m - b;
            } else {
                ans += c;
                c = 0;
            }
        }

        cout << ans << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Класс состоит из двух рядов и m мест в них. Даны обезьяны, которые хотят сидеть в первом ряду, во втором и те которым без разницы. Обезьяны не могут садится на ряд на который не хотят.
	Решение: Сначала сажать по своим местам, потом добавлять тех кому без разницы.