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

int main() {
    int t; cin >> t;

    for (int i = 0; i < t; ++i) {
        unordered_set<int> st;
        bool flag = true;

        int n; cin >> n;
        int num; cin >> num;
        st.insert(num);
        for (int j = 0; j < n-1; ++j) {
            cin >> num;
            if (st.find(num-1) == st.end() && st.find(num+1) == st.end()) {
                flag = false;
            }
            st.insert(num);
        }
        cout << ((flag) ? "YES" : "NO") << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Узнать правильно ли расселись по местам люди в автобусе.
	Решение: Сохранять занятые месте в хеш таблице. И проверять что места слева и справа заняты, если нет, значит кто-то сел напраивльно.