**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <unordered_set>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        unordered_set<char> st;
        int n; cin >> n;
        int ans = 0;
        for (int j = 0; j < n; ++j) {
            char c; cin >> c;
            if (st.find(c) == st.end()) {
                ans += 2;
                st.insert(c);
            } else {
                ++ans;
            }
        }
        cout << ans << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана строка, нужно проверить что все эти символы равны строке "Timur" в любом порядке.
	Решение: Отсортировать правильную строку, получить введенную строку, ее тоже отсортировать и сравнить.