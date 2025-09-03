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
    int n, m; cin >> n >> m;

    int count = m;
    vector<char> prime(count+1, true);
    prime[0] = prime[1] = false;

    for (long long i = 2; i*i <= count; ++i) {
        if (prime[i]) {
            for (long long j = i*i; j <= count; j += i) {
                prime[j] = false;
            }
        }
    }

    for (int i = n+1; i < m; ++i) {
        if (prime[i]) {
            cout << "NO" << endl;
            return 0;
        }
    }

    if (prime[m]) {
        cout << "YES" << endl;
    } else {
        cout << "NO" << endl;
    }

    return 0;
}
```
**Explanation:**
	Цель: Дано два числа. Первое простое. Требуется узнать является ли второе число следующим простым.
	Решение: С помощью решета Эратосфена узнать какие числа простые.
	Потом пройтись от n до m, ищя простые числа, если есть значит вывести NO. Иначе, если m - простое, то вывести YES, иначе вывести NO.1