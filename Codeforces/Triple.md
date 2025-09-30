**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(N)
Code:
Solution:
```cpp
#include <iostream>
#include <unordered_map>

using namespace std;

int main() {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        unordered_map<int, int> mp;
        int ans = -1;

        int n; cin >> n;
        for (int j = 0; j < n; ++j) {
            int num; cin >> num;
            ++mp[num];
            if (mp[num] >= 3) {
                ans = num;
            }
        }

        cout << ans << endl;
    }
    return 0;
}
```
**Explanation:**
	Цель: Найти число, которое повторяется три раза, иначе вывести -1.
	Решение: Сохранять число и коичество его повторений в хэш таблице. Если количесвтоповторений больше ии равно трем, то это число является ответом.