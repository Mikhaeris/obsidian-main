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
    unordered_map<int, int> mp;
    int n; cin >> n;
    while (n--) {
        int m; cin >> m;
        ++mp[m];
    }
    
    int m_max = 0, m_count = 0;
    for (const auto& m : mp) {
        if (m.second > m_count) {
            m_max = m.first;
            m_count = m.second;
        }
    }

    cout << m_count << endl;
    return 0;
}
```
**Explanation:**
	Цель: Даны монеты, их можно класть только в разные карманы. Узнать сколько карманов понадобится, чтобы поместить все монеты.
	Решение: Посчитать количество каждой монеты и вывести сколько раз встречается максимальная.