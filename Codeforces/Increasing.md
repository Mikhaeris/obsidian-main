**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
#include <iostream>
#include <unordered_map>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        int n; cin >> n;
        unordered_map<int, int> mp;
        bool flag = true;
        for (int j = 0; j < n; ++j) {
            int num; cin >> num;
            if (++mp[num] > 1) {
                flag = false;
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
	Цель: Дан массив, нужно проверить, что после перестановки массив станет строго возврастающим.
	Решение: Проверять, что каждый элемент в массиве встречается один раз.