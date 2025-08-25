**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main () {
    unordered_set<char> st = { 'c', 'o', 'd', 'e', 'f', 'r', 's'};

    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        char c; cin >> c;
        if (st.find(c) != st.end()) {
            cout << "YES" << endl;
        } else {
            cout << "NO" << endl;
        }
    }

    return 0;
}
```
**Explanation:**
	Цель: Проверть, содержится ли эта буква в слове "codeforces"
	Решение: Создать хеш сет [[Hash set]], где хранятся все буквы и проверять содержатся ли они там и выводить ответ.