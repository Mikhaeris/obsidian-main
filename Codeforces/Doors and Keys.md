**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <string>
#include <unordered_set>

using namespace std;

int main() {
    int t; cin >> t;
    while (t--) {
        unordered_set<char> st;
        bool flag = true;

        string s; cin >> s;
        for (auto& ch : s) {
            if (ch == 'r' || ch == 'g' || ch == 'b') {
                st.insert(ch);
            } else {
                char cl = tolower(ch);
                if (st.find(cl) == st.end()) {
                    flag = false;
                }
            }
        }
        (flag)
        ? cout << "YES" << endl
        : cout << "NO" << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Даны ключи и двери, нужно узнать, можно ли дойти до конца.
	Решение: Собирать ключи в хеш таблицу и когда встречается дверь проверить, что ключ для данной двери есть, инане невозможно пройти.