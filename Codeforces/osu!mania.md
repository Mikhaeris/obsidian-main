**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int n; cin >> n;
        vector<int> vec;
        for (int j = 0; j < n; ++j) {
            for (int k = 0; k < 4; ++k) {
                char ch; cin >> ch;
                if (ch == '#') {
                    vec.push_back(k+1);
                }
            }
        }

        for (int j = n-1; j >= 0; --j) {
            cout << vec[j];
        }
        cout << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Дана последовательность битов, нужно указать позиции в которые нужно нажимать.
	Решение: Собирать позиции и потом вывести в обратном порядке.