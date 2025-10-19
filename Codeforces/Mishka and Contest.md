**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <vector>

using namespace std;

int main() {
    int n, k; cin >> n >> k;

    vector<int> vec(n);
    for (int i = 0; i < n; ++i) {
        cin >> vec[i];
    }
    
    int count = 0;
    int l = 0, r = n - 1;
    while ((vec[l] <= k || vec[r] <= k) && l <= r) {
        if (vec[l] <= k) {
            ++count;
            ++l;
            continue;
        }

        if (vec[r] <= k) {
            ++count;
            --r;
            continue;
        }
    }

    cout << count << endl;

    return 0;
}
```
**Explanation:**
	Цель: Есть задачи, можно решать только с концов. Дано число, уровень сложности до которого задачи получится решить. Узнать сколько задач получится решить.
	Решение: Два указателя. Проходитя пока получается решить задачи.