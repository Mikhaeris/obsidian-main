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
    unordered_map<int, int> mp;
    int n, k; cin >> n >> k;

    int count = 0;
    for (int i = 0; i < n; ++i) {
        int num; cin >> num;
        if (mp.find(num) == mp.end()) {
            ++count;
            mp[num] = i+1;
        }
    }
    
    if (count >= k) {
        cout << "YES\n";
        int nc = 0;
        for (const auto& pr : mp) {
            cout << pr.second << ' ';
            if (++nc == k) {
                break;
            }
        }
    } else {
        cout << "NO\n";
    }
    cout.flush();
    return 0;
}
```
**Explanation:**
	Цель: Есть ученики с каким-то рейтингом. Нужно состаивть команду из этих учеников, чтобы их рейтинг был разный, если это возможно, то вывести номера этих учеников.
	Решение: Собирать в хэш таблицу рейтинг и номер ученика, чтобы они не совпадали. Если получаетя составить, то вывести номера этих учеников.