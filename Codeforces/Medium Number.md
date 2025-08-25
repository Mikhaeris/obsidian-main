**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <set>

using namespace std;

int main () {
    int t = 0; cin >> t;
    for (int i = 0; i < t; ++i) {
        set<int> st;
        for (int j = 0; j < 3; ++j) {
            int num; cin >> num;
            st.insert(num);
        }
        cout << *(++st.begin()) << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Даны три числа, нужно вывести среднее из них.
	Решение: Пихать в сет и вывести первый элемент.