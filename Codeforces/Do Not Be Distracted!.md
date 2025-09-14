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
        int n; cin >> n;
        cin.ignore();
        unordered_set<char> st;

        bool flag = true;
        char c, prev = getchar();
        while ((c = getchar()) != '\n') {
            if (c != prev) {
                if (st.find(c) != st.end()) {
                    flag = false;
                } else {
                    st.insert(prev);
                }
            }
            prev = c;
        }

        (flag)
        ? cout << "YES" << endl
        : cout << "NO" << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Поликарп решает задачи какждый день. Какдый день он модет решать тольок одну задачу. Он может решать их в любом порядке. Если он начал решать какую-то задачу, то должен решить ее до конца. Проверить соблюдал ли Поликарп все эти условия.
	Решение: В сет запихивать задачи, которые он предполодительно решил. Если после встретилась такая задача в сете, то сменить флаг. В зависимости от флага вывест ответ.