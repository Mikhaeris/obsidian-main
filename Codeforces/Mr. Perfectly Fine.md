**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <climits>

using namespace std;

typedef unsigned long long ull;

int main() {
    int t; cin >> t;
    while (t--) {
        int n; cin >> n;

        ull fm = INT_MAX, sm = INT_MAX, bm = INT_MAX;
        while (n--) {
            ull num; cin >> num;
            string s; cin >> s;
            
            if (s[0] == '1' && s[1] == '1') {
                bm = min(bm, num);
            } else if (s[0] == '1' && s[1] == '0') {
                fm = min(fm, num);
            } else if (s[0] == '0' && s[1] == '1') {
                sm = min(sm, num);
            }
        }

        if ((fm + sm) > INT_MAX && bm == INT_MAX) {
            cout << -1 << endl;
            continue;
        }

        cout << min(fm + sm, bm) << '\n';
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Даны книги навыки которые они дают и время, которое нужно на 
	Решение: Сначала сажать по своим местам, потом добавлять тех кому без разницы.