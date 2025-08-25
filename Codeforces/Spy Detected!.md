**Complexity:** 800
Answer:
	Time Complexity: O(N)
	Space Complexity: O(1)
Code:
Solution:
```cpp
##include <iostream>
#include <unordered_map>
#include <utility>

using namespace std;

int main () {
    int t; cin >> t;
    for (int i = 0; i < t; ++i) {
        unordered_map<int, pair<int, int>> mp;
        int n; cin >> n;
        for (int j = 0; j < n; ++j) {
            int num; cin >> num;
            ++mp[num].first;
            mp[num].second = j;
        }

        for (const auto &pr : mp) {
            if (pr.second.first == 1) {
                cout << pr.second.second+1 << endl;
            }
        }
    }
    return 0;
}
```
**Explanation:**
	Цель: Нужно найти число, которое отиливается от других.
	Решение: Самый странный вариант хранения - хеш таблица, ключ - число, значение - пара - количество, последняя встречающаяся позиция. Где количество повторений одно вернуть последнюю встречающуюся позицию